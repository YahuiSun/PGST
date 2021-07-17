# Approximating Probabilistic Group Steiner Trees in Graphs

The introduction of these files are as follows. 


# Datasets

<b>The Amazon dataset</b> is in the amazon folder. The dictionary is as follows.

Each column of "amazon_items.txt" contains the information of an item: "Item_ID, Average_rating_of_this_item, Keywords_of_this_item". For example, "<itemid>3<itemid/><avg_rating>5<avg_rating/>\<keywords\>100000009,100000010<keywords/>" means that Item 3 has an average rating of 5, and the keywords associated with Item 3 are 100000009 and 100000010. There are 548552 items in total.

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




<b>The Wikipedia dataset</b> is in the Wiki_1M folder. The dictionary is as follows.

page_num = 1176192 page_connection_num = 11124449

In "Wiki_pages_1176k_undirected.txt", an example line content is "0 Lily_Laita", 
which means that the name of page 0 is Lily_Laita.

In "Wiki_pagerelationships_1176k_undirected.txt", an example line content is "422690 1158259", 
which means that page 422690 is linked to page 1158259.

Each pageview file, e.g., "pageviews_1176k_2020_1_1.txt",  records the pageview data for a day.
An example line content in a page view file is "607329 2 F1W1", 
which means that the total pageview of page 607329 in this day is 2, and the detail of this pageview is F1W1, and 
<Hour: from 0 to 23, written as 0 = A, 1 = B ... 22 = W, 23 = X>, i.e., F1W1 means that there is 1 pageview in hour F
and 1 pageview in hour W



# C++ codes 

The C++ source codes are in <b>TBH.cpp</b>. 

It is recommended to fold all the regions of codes for easy reading (by pressing Ctrl+M+O in Visual Studio). 

Running these codes requires some header files (e.g. #include <graph_hash_of_mixed_weighted/graph_hash_of_mixed_weighted.h>; see cppheader_2021****.zip) and the Boost library: https://www.boost.org/ (e.g. #include <boost/random.hpp>) . 

<b>After making the header files ready, some example experiments can be conducted by running the function "example_experiments()", we have provided some comments/instructions inside this function. All the experiments in our paper can be produced in the same way as "example_experiments()".</b>

To read these C++ codes in detail, it is recommended to start from "example_experiments()", and then go to "experiment_element". More detailed codes in other regions can then be traced. There are some directions on these codes as follows. 

1) The codes of our MIRROR and S-MIRROR algorithms are below "/*accelerated_MIRROR and accelerated_S_MIRROR*/"
2) The codes of our H-MIRROR and H-S-MIRROR algorithms are below "/*accelerated_H_MIRROR and accelerated_H_S_MIRROR*/"
3) The codes of baseline algorithms are below "/*adapted static algorithms for hunting temporal bumps*/"

