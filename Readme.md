**Pre-requirements:**

------

1. **Java enviroment: Java 1.7 or 1.8 JDK:**

- [Java 1.7 or 1.8 JDK](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html). ([Alternative link](http://tecadmin.net/install-oracle-java-8-jdk-8-ubuntu-via-ppa/) for Ubuntu/LinuxMint). Minimum system requirements for running Java can be found at http://java.com/en/download/help/sysreq.xml

- [Latest Juicer Tools jar](https://github.com/theaidenlab/juicer/wiki/Download)

  

2. **Some packages from python**

   Python 3.9(I used)

   numpy, pathlib which you can easily install it at command. 

   In case you don't want search on the web: pip install numpy and pip install pathlib

   

3. **converse_to_hic.py**

    PS: This is only for 1169*1169, and the format should be(You could make some changes to let it fit in your maps): <img width="776" height="52" alt="image-20250512144059609" src="https://github.com/user-attachments/assets/f2a58f87-86e5-452f-a498-3d0a781b58d7" />


   

4. **Map files which you want to convert** 

   You need to process it onr by one for now

------

**Convert .map to .hic Tutorial:**

1. The only thing you need to change is MAP_FILES that you can easily find it in my code.

Or you can see this picture blow, I made some mark for understanding.

<img width="936" height="616" alt="image-20250512144920611" src="https://github.com/user-attachments/assets/ad2b3f47-928b-415e-9f9e-abad8ddbefa1" />




2. Then just run this code.

   You will get .hic file successfully!!!


**Convert .hic to .csv(.map) Tutorial:**
1. Upload .hic file on JuiceBox to check chromosome and the Bin size.(Ex. chr11:1-122,082,543 chr11:1-122,082.543 Bin Size: 250kb, Norm = None)

2. Use juicerTools to get initial matrix  (Ex. java -jar Tools/juicer_tools_1.22.01.jar dump observed NONE "E:/chro_research/Week10/mouse_Big_hicmap/cellnames_cluster_4.hic" chr11:1:122082543 chr11:1:122082543 BP 250000 mouse_cluster4_chr11_250kb.txt
)

3. Use gernerated txt file as input for convert_from_hic_to_csv.py

4. Run convert_from_hic_to_csv.py, get the csv(map) file.


**Combine two hic map to one box Tutorial:**
Set right path in Combine_2hic.py and Run it.










Ps:


You can find all of commands for Juicer_tool in this link:https://github.com/aidenlab/juicer/wiki/Pre
