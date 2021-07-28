# omicsGAN
omicsGAN is the generative adversarial network based framework that can integrate two omiocs data along with their interaction network to generate one synthetic data corresponding to each omics profile that can result in a better phenotype prediction. 


### **Framework**
![Image description](https://github.com/compbiolabucf/omicsGAN/blob/main/netflow-1.png)

<!---
## **BRCA_mRNA.py**
The framework to update mRNA expression for breast cancer (update k). It takes <img src="https://render.githubusercontent.com/render/math?math=H_x^{(k-1)}"> and 
<img src="https://render.githubusercontent.com/render/math?math=H_y^{(k-1)}"> as input and generates <img src="https://render.githubusercontent.com/render/math?math=H_x^{(k)}"> . User has to define the value of variable **update** that represents the value of k in the generated data. 

## **BRCA_miRNA.py**
The framework to update miRNA expression for breast cancer (update k). It takes <img src="https://render.githubusercontent.com/render/math?math=H_y^{(k-1)}"> and 
<img src="https://render.githubusercontent.com/render/math?math=H_x^{(k-1)}"> as input and generates <img src="https://render.githubusercontent.com/render/math?math=H_y^{(k)}"> . User has to define the value of variable **update** that represents the value of k in the generated data. 

## **rand_mRNA_BRCA.py**
The framework to update mRNA expression for breast cancer (update k) using a random network. It takes <img src="https://render.githubusercontent.com/render/math?math=H_x^{(k-1)}"> and <img src="https://render.githubusercontent.com/render/math?math=H_y^{(k-1)}"> as input and generates <img src="https://render.githubusercontent.com/render/math?math=H_x^{(k)}"> . User has to define the value of variable **update** that represents the value of k in the generated data and **serial** that indicates the number of random network being used (serial=[1,2,...10]). It generates multiple synthetic data at multiple epochs and saves them at the current directory. As there are multiple phenotypes to be predicted, based on the printed validation AUC, user has to choose the best epoch and the corrosponding sythetic data.   

## **rand_miRNA_BRCA.py**
The framework to update miRNA expression for breast cancer (update k) using a random network. It takes <img src="https://render.githubusercontent.com/render/math?math=H_y^{(k-1)}"> and <img src="https://render.githubusercontent.com/render/math?math=H_x^{(k-1)}"> as input and generates <img src="https://render.githubusercontent.com/render/math?math=H_y^{(k)}"> . User has to define the value of variable **update** that represents the value of k in the generated data and **serial** that indicates the number of random network being used (serial=[1,2,...10]). It generates multiple synthetic data at multiple epochs and saves them at the current directory. As there are multiple phenotypes to be predicted, based on the printed validation AUC, user has to choose the best epoch and the corrosponding sythetic data.   


## **OV_mRNA.py**
The framework to update mRNA expression for ovarian cancer (update k). It takes <img src="https://render.githubusercontent.com/render/math?math=H_x^{(k-1)}"> and 
<img src="https://render.githubusercontent.com/render/math?math=H_y^{(k-1)}"> as input and generates <img src="https://render.githubusercontent.com/render/math?math=H_x^{(k)}"> . User has to define the value of variable **update** that represents the value of k in the generated data. 

## **OV_miRNA.py**
The framework to update miRNA expression for ovarian cancer (update k). It takes <img src="https://render.githubusercontent.com/render/math?math=H_y^{(k-1)}"> and 
<img src="https://render.githubusercontent.com/render/math?math=H_x^{(k-1)}"> as input and generates <img src="https://render.githubusercontent.com/render/math?math=H_y^{(k)}"> . User has to define the value of variable **update** that represents the value of k in the generated data. 

## **LUAD_mRNA.py**
The framework to update mRNA expression for lung cancer (update k). It takes <img src="https://render.githubusercontent.com/render/math?math=H_x^{(k-1)}"> and 
<img src="https://render.githubusercontent.com/render/math?math=H_y^{(k-1)}"> as input and generates <img src="https://render.githubusercontent.com/render/math?math=H_x^{(k)}"> . User has to define the value of variable **update** that represents the value of k in the generated data. 

## **LUAD_miRNA.py**
The framework to update miRNA expression for lung cancer (update k). It takes <img src="https://render.githubusercontent.com/render/math?math=H_y^{(k-1)}"> and 
<img src="https://render.githubusercontent.com/render/math?math=H_x^{(k-1)}"> as input and generates <img src="https://render.githubusercontent.com/render/math?math=H_y^{(k)}"> . User has to define the value of variable **update** that represents the value of k in the generated data. 

--->


## Required Python packages
- Numpy (>=1.17.2)
- Pandas (>=0.25.1)
- sklearn (>=0.21.3)
- PyTorch (pytorch version >=1.5.0, torchvision version >=0.6.0)

## Sample datasets 
Sample datasets for breast cancer phenotype prediction are available below.\
mRNA expression: https://drive.google.com/file/d/13WNOJltciCOsa2I5gHK15mgKj6qx8KHT/view?usp=sharing \
miRNA expression: https://drive.google.com/file/d/1MIKtpmsozOWmSbUiLcXc24lI21WCi1qh/view?usp=sharing \
interaction network: https://drive.google.com/file/d/13AssxLZQdta4O-9bQhHaSgSuaslnJceO/view?usp=sharing \
label data: https://drive.google.com/file/d/1MyRZ_vjsBZMSuDQDBdnkdcWiFJb1G5tW/view?usp=sharing


## Codes
**omicsGAN.py**
Users only need to run this code for generating synthetic data through omicsGAN using command line arguments mentioned above.  

**omics1.py**
Called from omicsGAN.py and updates the first omics data

**omics2.py**
Called from omicsGAN.py and updates the second omics data


## Quick start guide
Users need to download all data necessary for a cancer analysis into the same folder as the three codes. Updated omics datasets will be saved in the same folder as well. 

**Input data:**
All input data is in csv format.
***omics data:***
Omics datasets should be in feature by sample format with first column being the names of the features and first row being names of the samples. \
![Image description](https://github.com/compbiolabucf/omicsGAN/blob/main/Omics1.PNG) 
![Image description](https://github.com/compbiolabucf/omicsGAN/blob/main/Omics2.PNG) 
<!---If more than one cancer types are to be analyzed simulataneously, they must be stored in different directories as some datasets have duplicate names.--->
 and interaction netowrk should be in first omics data by second omics data format. Label data should be a column vector with each row corresponding to a sample. All datasets should be comma separated values. To run the code use the command \
**Command:** omicsGAN.py, total number of update(K), first omics dataset, second omics dataset, interaction network, label 

For example, to generate synthtic mRNA and miRNA expression using our provided dataset, users have to use the following command  
**Sample command:** omicsGAN.py 5 mRNA.csv miRNA.csv bipartite_targetscan_gene.csv label.csv

For any concern or further assistance, contact t.ahmed@knights.ucf.edu
