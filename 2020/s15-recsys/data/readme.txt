
=======================
hetrec2011-movielens-2k
=======================

-------
Version
-------

Version 1.0 (May 2011)

-----------
Description
-----------

    This dataset is an extension of MovieLens10M dataset, published by GroupLeans 
    research group.
    http://www.grouplens.org 
    
    It links the movies of MovieLens dataset with their corresponding web pages at 
    Internet Movie Database (IMDb) and Rotten Tomatoes movie review systems.
    http://www.imdb.com 
    http://www.rottentomatoes.com 

    From the original dataset, only those users with both rating and tagging information 
    have been mantained.
    
    The dataset is released in the framework of the 2nd International Workshop on 
    Information Heterogeneity and Fusion in Recommender Systems (HetRec 2011) 
    http://ir.ii.uam.es/hetrec2011 
    at the 5th ACM Conference on Recommender Systems (RecSys 2011)
    http://recsys.acm.org/2011 

---------------
Data statistics
---------------

    2113 users
   10197 movies
   
      20 movie genres
   20809 movie genre assignments
         avg. 2.040 genres per movie

    4060 directors
   95321 actors
         avg. 22.778 actors per movie
      72 countries

   10197 country assignments
         avg. 1.000 countries per movie
   47899 location assignments
         avg. 5.350 locations per movie

   13222 tags
   47957 tag assignments (tas), i.e. tuples [user, tag, movie]
         avg. 22.696 tas per user
         avg. 8.117 tas per movie

  855598 ratings
         avg. 404.921 ratings per user
         avg. 84.637 ratings per movie

-----
Files
-----

   * movies.dat
   
   	This file contains information about the movies of the database.
   	
   	The original movie information -title and year- available at MovieLens10M dataset 
   	has been extended with public data provided in IMDb and Rotten Tomatoes websites:
   	   - Titles in Spanish
   	   - IMDb movie ids
   	   - IMDb picture URLs
           - Rotten Tomatoes movie ids
           - Rotten Tomatoes picture URLs
           - Rotten Tomatoes (all/top) critics' ratings, avg. scores, numbers of 
             reviews/fresh_scores/rotten_scores
           - Rotten Tomatoes audience' avg. ratings, number of ratings, avg. scores
   
   * movie_genres.dat
   
        This file contains the genres of the movies.
   
   * movie_directors.dat
   
   	This file contains the directors of the movies.
   
   * movie_actors.dat
   
   	This file contains the main actores and actresses of the movies.
   	
   	A ranking is given to the actors of each movie according to the order in which 
   	they appear on the movie IMDb cast web page.
   
   * movie_countries.dat
   
        This file contains the countries of origin of the movies.
   
   * movie_locations.dat
   
        This file contains filming locations ot the movies.
   
   * tags.dat
   
   	This file contains the set of tags available in the dataset.
   
   * user_taggedmovies.dat - user_taggedmovies-timestamps.dat
   
        These files contain the tag assignments of the movies provided by each particular user.
        
        They also contain the timestamps when the tag assignments were done.
   
   * movie_tags.dat
   
        This file contains the tags assigned to the movies, and the number of times 
        the tags were assigned to each movie.
   
   * user_ratedmovies.dat - user_ratedmovies-timestamps.dat
   
        These files contain the ratings of the movies provided by each particular user.
        
        They also contain the timestamps when the ratings were provided.

-----------
Data format
-----------

   The data is formatted one entry per line as follows (tab separated, "\t"):

   * movies.dat
   
        id \t title \t imdbID \t spanishTitle \t imdbPictureURL \t year \t rtID \t rtAllCriticsRating \t rtAllCriticsNumReviews \t rtAllCriticsNumFresh \t rtAllCriticsNumRotten \t rtAllCriticsScore \t rtTopCriticsRating \t rtTopCriticsNumReviews \t rtTopCriticsNumFresh \t rtTopCriticsNumRotten \t rtTopCriticsScore \t rtAudienceRating \t rtAudienceNumRatings \t rtAudienceScore \t rtPictureURL

        Example:
        1	Toy story	0114709	Toy story (juguetes)	http://ia.media-imdb.com/images/M/MV5BMTMwNDU0NTY2Nl5BMl5BanBnXkFtZTcwOTUxOTM5Mw@@._V1._SX214_CR0,0,214,314_.jpg	1995	toy_story	9	73	73	0	100	8.5	17	17	0	100	3.7	102338	81	http://content7.flixster.com/movie/10/93/63/10936393_det.jpg

   * movie_genres.dat
   
        movieID	\t genre

        Example:
        1	Adventure

   * movie_directors.dat

        movieID \t directorID \t directorName

        Example:
        1	john_lasseter	John Lasseter
   
   * movie_actors.dat

        movieID \t actorID \t actorName \t ranking

        Example:
        1	annie_potts	Annie Potts	10
   
   * movie_countries.dat

        movieID \t country

        Example:
        1	USA

   * movie_locations.dat

        movieID \t location1 \t location2 \t location3 \t location4

        Example:
        2	Canada	British Columbia	Vancouver
   
   * tags.dat

        id \t value

        Example:
        1	earth

   * movie_tags.dat

        movieID \t tagID \t tagWeight

        Example:
        1	13	3
   
   * user_taggedmovies-timestamps.dat

        userID \t movieID  \t tagID  \t timestamp

        Example:
        75	353	5290	1162160415000
        
   * user_taggedmovies.dat

        userID \t movieID \t tagID \t date_day \t date_month \t date_year \t date_hour \t date_minute \t date_second

        Example:
        75	353	5290	29	10	2006	23	20	15
   
   * user_ratedmovies-timestamps.dat

        userID \t movieID \t rating \t timestamp

        Example:
        75	3	1	1162160236000

   * user_ratedmovies.dat

        userID \t movieID \t rating \t date_day \t date_month \t date_year \t date_hour \t date_minute \t date_second

        Example:
        75	3	1	29	10	2006	23	17	16

------- 
License
-------

   The data contained in hetrec2011-movielens-2k.zip is distributed with permission of GroupLens research group.
   
   The data is made available for non-commercial use.
   
   Those interested in using the data in a commercial context should contact GroupLens members:
   http://www.grouplens.org/contact

----------------
Acknowledgements
----------------

   We thank GroupLens research group at University of Minessota (http://www.grouplens.org) 
   for hosting and allowing us to publish this dataset, which is an extension of MovieLens10M dataset.

   This work was supported by the Spanish Ministry of Science and Innovation (TIN2008-06566-C04-02), 
   and the Regional Government of Madrid (S2009TIC-1542).

----------
References
----------

   When using this dataset you should cite:
      - the original Movielens dataset from GroupLens research group, http://www.grouplens.org
      - IMDb website, http://www.imdb.com
      - Rotten Tomatoes website, http://www.rottentomatoes.com

   You may also cite HetRec'11 workshop as follows:

   @inproceedings{Cantador:RecSys2011,
      author = {Cantador, Iv\'{a}n and Brusilovsky, Peter and Kuflik, Tsvi},
      title = {2nd Workshop on Information Heterogeneity and Fusion in Recommender Systems (HetRec 2011)},
      booktitle = {Proceedings of the 5th ACM conference on Recommender systems},
      series = {RecSys 2011},
      year = {2011},
      location = {Chicago, IL, USA},
      publisher = {ACM},
      address = {New York, NY, USA},
      keywords = {information heterogeneity, information integration, recommender systems},
   } 

-------
Credits
-------

   This dataset was built by Iván Cantador with the collaboration of Alejandro Bellogín and Ignacio Fernández-Tobías, 
   members of the Information Retrieval group at Universidad Autonoma de Madrid (http://ir.ii.uam.es)

-------   
Contact
-------

   Iván Cantador, ivan [dot] cantador [at] uam [dot] es
