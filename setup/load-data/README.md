## Load Data

Certain Cassandra Day notebooks need a keyspace, schema, and data set loaded. The instructions below will guide you through loading the data needed for all notebooks.

The commands here make use of the **cqlsh** tool, which comes installed with DataStax Enterprise. If **cqlsh** is not already in your `/usr/bin` directory, such as with the package install, you'll need to modify the commands to execute **cqlsh** from wherever it is installed in your local environment.
### Creating a keyspace

#### Keyspace: killrvideo
```
cqlsh -e "CREATE KEYSPACE killrvideo WITH replication = {'class': 'SimpleStrategy', 'replication_factor': 1};"
```

### Creating the tables

Run these commands from the root of this repo, or adjust the path to `schema.cql` file to point to the location where you cloned the repo.

#### Keyspace: killrvideo
```
cqlsh -k killrvideo -f data/schema/schema.cql
```

### Loading data

Run these commands from the root of this repo, or adjust the path to the csv files to point to the location where you cloned the repo.

#### Keyspace: killrvideo
```
cqlsh -k killrvideo -e "COPY users FROM 'data/csv/users.csv';"
cqlsh -k killrvideo -e "COPY videos_by_tag FROM 'data/csv/videos_by_tag.csv';"
cqlsh -k killrvideo -e "COPY user_credentials FROM 'data/csv/user_credentials.csv';"
cqlsh -k killrvideo -e "COPY tags_by_letter FROM 'data/csv/tags_by_letter.csv';"
cqlsh -k killrvideo -e "COPY video_playback_stats FROM 'data/csv/video_playback_stats.csv';"
cqlsh -k killrvideo -e "COPY latest_videos FROM 'data/csv/latest_videos.csv';"
cqlsh -k killrvideo -e "COPY video_ratings_by_user FROM 'data/csv/video_ratings_by_user.csv';"
cqlsh -k killrvideo -e "COPY comments_by_user FROM 'data/csv/comments_by_user.csv';"
cqlsh -k killrvideo -e "COPY videos FROM 'data/csv/videos.csv';"
cqlsh -k killrvideo -e "COPY comments_by_video FROM 'data/csv/comments_by_video.csv';"
cqlsh -k killrvideo -e "COPY user_videos FROM 'data/csv/user_videos.csv';"
```
