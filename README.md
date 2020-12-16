# Multilevel Text Clustering
#### Data Set: 
The Multimodal Attribute Extraction (MAE) dataset is the first benchmark dataset for the task of multimodal attribute extraction. It is composed of mixed media data for 2.2 million product items. For each item there is a textual description, set of product images, and open-schema table of product attributes. For more informatiom refer [here.](https://rloganiv.github.io/mae/)

Training Data: `wget https://s3-us-west-2.amazonaws.com/mumie/train.zip`

Validation Data: `wget https://s3-us-west-2.amazonaws.com/mumie/val.zip`

Images: `https://s3-us-west-2.amazonaws.com/mumie/img.tar.gz`

#### Setup

```python
git clone https://github.com/RatulGhosh/Multilevel-Text-Clustering.git
cd Multilevel-Text-Clustering
pip install -r requirements.txt
```
Run directly on google colab:

First level clustering           |  Cultering on electronics & clothing items
:-------------------------:|:-------------------------:
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1Zi76bCNJ1icCDizG6pvjFZvEuMZvqB2S?usp=sharing)   |  [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1q5ypw61btwp0E7odg_ggFxVrDwPvGSMC?usp=sharing) 



#### Results:
Here we tried doing clustering using only the product's description and tried creating a taxonomy. We used [Sentence-BERT](https://arxiv.org/pdf/1908.10084.pdf) which fine-tune BERT for the semantic similarity between sentences using a siamese network structure. Sentence-BERT takes the product description as an input and outputs a fixed-sized vector representing the semantic of that sentence. We then use that vector to categorize these products into multiple clusters. Our preliminary analysis shows there is a total of 9 categories. 
Then we filtered all the product descriptions from two categories Electronics and Clothing and did another level of clustering on each of those.  
* Electronics are getting clustered into categories camera, audio devices, computers, computer accessories, and phone.
* Clothing is getting clustered into winterwear, bottom-wear, womenswear, and footwear.

The figures below show some of the clusters for electronics and clothes.

#### ***Clustering on electronics items:***
Audio Devices            |  Camera & Lens
:-------------------------:|:-------------------------:
![](https://raw.githubusercontent.com/RatulGhosh/Multilevel-Text-Clustering/main/demos/audios.png)  |  ![](https://raw.githubusercontent.com/RatulGhosh/Multilevel-Text-Clustering/main/demos/cameras.png)

PC related          |  Phones & Accesories 
:-------------------------:|:-------------------------:
![](https://raw.githubusercontent.com/RatulGhosh/Multilevel-Text-Clustering/main/demos/pc.png)  |  ![](https://raw.githubusercontent.com/RatulGhosh/Multilevel-Text-Clustering/main/demos/phones.png)

#### ***Clustering on clothing items:***
Audio Devices            |  Camera & Lens
:-------------------------:|:-------------------------:
![](https://raw.githubusercontent.com/RatulGhosh/Multilevel-Text-Clustering/main/demos/audios.png)  |  ![](https://raw.githubusercontent.com/RatulGhosh/Multilevel-Text-Clustering/main/demos/cameras.png)

Bottomwear          |  Shoes
:-------------------------:|:-------------------------:
![](https://raw.githubusercontent.com/RatulGhosh/Multilevel-Text-Clustering/main/demos/bottom_wear.png)  |  ![](https://raw.githubusercontent.com/RatulGhosh/Multilevel-Text-Clustering/main/demos/footwear.png)

Womenswear          |  Winter Clothes
:-------------------------:|:-------------------------:
![](https://raw.githubusercontent.com/RatulGhosh/Multilevel-Text-Clustering/main/demos/womenswear.png)  |  ![](https://raw.githubusercontent.com/RatulGhosh/Multilevel-Text-Clustering/main/demos/winter_wear.png)



