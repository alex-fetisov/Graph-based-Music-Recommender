# Graph-based-Music-Recommender

This is Week 5 taks of the Big Data course.

<H3>Graph based Music Recommender. Task 1</H3>
Data description (DataFrames in parquet format)
Location - /data/sample264

Fields: trackId, userId, timestamp, artistId

    trackId - id of the track
    userId - id of the user
    artistId - id of the artist
    timestamp - timestamp of the moment the user starts listening to a track

Location - /data/meta

Fields: type, Name, Artist, Id

    Type could be “track” or “artist”
    Name is the title of the track if the type == “track” and the name of the musician or group if the type == “artist”.
    Artist states for the creator of the track in case the type == “track” and for the name of the musician or group in case the type == “artist”.
    Id - id of the item

<h4>Task</h4>
Build the edges of the type “track-track”. To do it you will need to count the collaborative similarity between all the tracks: if a user has started listening to the tracks A and B together in the limited time interval (equal to 7 minutes), then you should add 1 to the weight of the edge from vertex A to vertex B (initial weight is equal to 0). For each track choose top 40 tracks ordered by weight similar to it and normalize weights of its edges (divide the weight of each edge on a summary of weights of all edges).

Sort the resulting Data Frame in descending order by the column norm_count, take top 40 rows, select only the columns “id1”, “id2”, sort them in ascending order this time first by “id1”, then by “id2” and print the columns “id1”, “id2” of the resulting dataFrame.

The part of the result on the sample dataset:

    ...
    798331 827364
    798335 840741
    798374 816874
    798375 810685
    798379 812055
    ...

For all subtasks use the same ipython notebook, each subtask should be the continuation of the previous

