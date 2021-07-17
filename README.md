# Approximating Probabilistic Group Steiner Trees in Graphs

The introduction of these files are as follows. 


# Datasets

<b>The Amazon dataset</b> is in the amazon folder. The dictionary is as follows.

Each column of "amazon_items.txt" contains the information of an item: "Item_ID, Average_rating_of_this_item, Keywords_of_this_item". For example, "\<itemid\>3\<itemid\/>\<avg_rating\>5\<avg_rating\/>\<keywords\>100000009,100000010\<keywords\/>" means that Item 3 has an average rating of 5, and the keywords associated with Item 3 are 100000009 and 100000010. There are 548552 items in total.

Each column of "amazon_keywords.txt" corresponds to a keyword, and contain the ID of a keyword and the name of this keyword. For example, "100000417	Sheldon, Jack" means that the keyword of "Sheldon, Jack" has an ID of 100000417. There are 25958 keywords in total.

Each column of "amazon_items_links.txt" contains the IDs of two items, and indicates that there are users who bought these two items at the Amazon website at the same time. We link such a pair of items. There are 987942 links in total.



<b>The Reddit dataset</b> is in the Reddit folder. The dictionary is as follows.

Community_num = 148873, Keyword_num = 591072, community_keyword_pair_num (dummy_vertex_num) = 1023334

In "Communities.txt", an example line content is "r/phinvest	1000035", 
which means that the ID of community "r/phinvest" is 1000035.

In "Keywords.txt", an example line content is "personal space	2", 
which means that the ID of keyword "personal space" is 2.

In "dummy_vertex_IDs.txt", an example line content is "1008668+287955	2247821", 
which means that the pair of community 1008668 and keyword 287955 has an ID of 2247821.


Each comment file, e.g., "Comments_2019_9_1.txt",  records the comment data for a day.
An example line content in a comment file is "2604152	6_2,7_5", 
which means that the details of comments corresponding to dummy vertex 2604152 (suppose that 2604152 corresponds to 
the pair of community X and keyword Y; then these comments are in community X and contain keyword Y) is 6_2,7_5,
i.e., there are 2 comments in hour 6 and 5 comments in hour 7 (the hour ID is from 0 to 23).




<b>The Movie dataset</b> is in the movie folder. The dictionary is as follows.

Each line of "MovieLens_25M_movie_info.txt" corresponds to the information of a movie: Movie_ID(start from 0):::Movie_name:::Average_star:::genres. For example, "5:::Homage (1995):::2.536:::6_Drama", which means that Movie 5 has a name of Homage (1995), and has an average rating star of 2.536, and the genre of this movie is Drama (the genre ID of Drama is 6). There are 62423 movies in total.

Each line of "MovieLens_25M_movie_links.txt" contains a pair of movies such that there are users who rate both these two movies five stars. The content in each line is "Movie_ID1(start from 0):::Movie_ID2(start from 0):::Number_of_common_5_star_raters". For example, "1252:::1395:::79" means that there are users who rate five stars to both Movies 1252 and 1395, and the number of such persons is 79. There are 35323774 pairs of movie in total.




# C++ codes 

The C++ source codes are in <b>TBH.cpp</b>. 

It is recommended to fold all the regions of codes for easy reading (by pressing Ctrl+M+O in Visual Studio). 

Running these codes requires some header files (e.g. #include <graph_hash_of_mixed_weighted/graph_hash_of_mixed_weighted.h>; see cppheader_2021****.zip) and the Boost library: https://www.boost.org/ (e.g. #include <boost/random.hpp>) . 

<b>After making the header files ready, some example experiments can be conducted by running the function "example_experiments()", we have provided some comments/instructions inside this function. All the experiments in our paper can be produced in the same way as "example_experiments()".</b>

To read these C++ codes in detail, it is recommended to start from "example_experiments()", and then go to "experiment_element". More detailed codes in other regions can then be traced. There are some directions on these codes as follows. 

1) The codes of our MIRROR and S-MIRROR algorithms are below "/*accelerated_MIRROR and accelerated_S_MIRROR*/"
2) The codes of our H-MIRROR and H-S-MIRROR algorithms are below "/*accelerated_H_MIRROR and accelerated_H_S_MIRROR*/"
3) The codes of baseline algorithms are below "/*adapted static algorithms for hunting temporal bumps*/"

