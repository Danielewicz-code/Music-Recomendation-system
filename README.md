# Music-Recomendation-system


# music recommendation

firstly have an audio dataset but there’s many so don´t worry about that, second a MAX Audio embedding generator approach to convert the audio data into vectors, that’s part one, then i need to make a model o find a model, a machine learning one, that can convert the vectors from the embedding into wave sounds again, maybe with ANNOY

New idea, after thinking a lot i came to realize i don´t have to use “real” music, just a dataset with music data itself, so that’s what i’m going to do, my idea is this: 

first of all, just pick a good dataset, i’m lucky and i found one dataset that can support the approach I want to make. The link for that follows here: https://www.kaggle.com/datasets/rodolfofigueroa/spotify-12m-songs/data

now i’m just checking the dataset to be sure its enough.

**Data management**: 

i think i can do it, the dataset was inconsistent, meaning it didn´t have basic things for this project, like the genre, lyrics, etc. But i think i did it, first of all i manage to put all the musical features together, an example of these would be: 

| 4 explicit 1204025 non-null bool
5 danceability 1204025 non-null float64
6 energy 1204025 non-null float64
7 key 1204025 non-null int64
8 loudness 1204025 non-null float64
9 mode 1204025 non-null int64
10 speechiness 1204025 non-null float64
11 acousticness 1204025 non-null float64
12 instrumentalness 1204025 non-null float64
13 liveness 1204025 non-null float64
14 valence 1204025 non-null float64
15 tempo 1204025 non-null float64
16 duration_ms 1204025 non-null int64
17 year |
| --- |

here we can see different features, so i put them all together to try to make something like a “genre” that in reality we humans cannot name but the machine learning algorithms can, so hopefully this will work so i can build this model. Tomorrow i’m going to do the vectorization process among other things.

**upload**: 

my laptop is shit and i needed to reduce the dimensionality by a LOT, we are talking that from 1.2 Million songs, I’m now using only 50,000 which is a lot but less than i wanted but i think it will work

**Vector Approach**:

now i’m going to use an approach for these vectors and this is cosine similarity, basically this algorithm give us the similarity based on the angle of the vectors. For example:

we have vectors: [A], [B] and [C]

A = [3, 2]

B = [6, 4]

C = [7, -2]

using this formula: cos(θ) = X * Y / ||X||  * ||Y||

that formula will give us a proximity, for example with A - B and A - C for the first two we first do a dot product so:

A * B =(3 * 6) + (2 * 4) = 18 + 8 = 26

||A|| = √(3)power of 2 + (2)power of 2 = 9 + 4 = 13 = 3.605

||B|| = √(6)power of 2 + (4)power of 2 = 36 + 16 = 52 = 7.211

so back to formula:  cos(θ) = (A * B) / (||A|| * ||B||) will be cos(θ) = ( 26) / (3.60 * 7.21) = 0.998

basically telling us that the similarity in these two vectors is of an 99% which makes sense since the two vectors are on the same line but at a different scale, now if we compare the vector A and C for example:

 

A * C = (3 * 7) + (2 * -2) = 21 - 4 = 17

||A|| = √(3^2 + 2^2) = √(9 + 4) = √13 ≈ 3.605
||C|| = √(7^2 + (-2)^2) = √(49 + 4) = √53 ≈ 7.280

back to formula it will be: Cos(θ) = (A * C) / (||A|| * ||C||) = 17 / (3.605 * 7.280) ≈ 0.317

which means that A and C only have a 31% similarity.

to use all this i’m going to use a library called ***sklearn:***

***from sklearn.metrics.pairwise import cosine_similarity***

**Web application:**

Now i need to Streamlit, to create web applications

at the end i couldn´t do it :)
