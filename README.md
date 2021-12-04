# LT_Project_shared_files
Shared files for the LT project.

The most useful files are distance_matrix.py, distances.txt and database.txt. (.txt files are in txt_files/)

distances.txt is a compilation of the datas obtained using the OSRM API on 1st Dec.
    
database.txt are cities datas. I don't use it to open/close manipulation: simply copy it's content and paste it in a .py file if you need it.
    
distance_matrix.py acts as an exemple of how to exploit the distances.txt datas to fill a distance matrix.
    
We could also fill a *duration* matrix, that may be more interesting regarding our problem (see 'mode' var.)
Note that when I upload this files, I only have datas between cities. Of course on may want additional datas, for instance 
with the truck center, etc. I tried to make this as simple as possible: 

1. You have to modify the parameter S which correspond to the size of the matrix you get
        
2. The method get_gps(int i) returns the gps coordinates of some cities using the content in the annex part. When i is > ~43 (number of cities), add some exception rules that returns the gps coordinates¹ of the locations you are interested in.
        
3. The file computes automatically² all the distances and duration with the call(string sd) function, and it *learns* it by expanding the distances.txt file.
        
        
¹: gps coordinates are in an unusual format. Check other gps coordinates but it should look like ~5;~45. You can get gps coordinates using https://www.gps-coordinates.net/. It does not need too much precision to work well.

²: API limitations makes it impossible to compute more than one travel every 5 seconds. If you add a bunch of locations you have not computed yet you should expect some long computation time. If you want to make sure the programm is actually working I recommand leaving the 'verbose' mode to True.

