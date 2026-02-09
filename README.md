# Kaggle 
This is the Kaggle challenge [Optiver - Trading at Close](https://www.kaggle.com/competitions/optiver-trading-at-the-close).
Done by me.

# Blog
Read my  [blog](https://www.lesterjones.nl/blog/3/optiver-trading-at-the-close) for a quick overview of the reason why this repository is made..

# Setup project 
In the repo below you will find two .ipynb files. <br/><br/>

The *all-models.ipynb file contains two linear regression models and one prophet model. <br/>
This version has the option to provide an insight of the Mean Average Error (MAE) of all models on the validation set. <br/>
Which is handy for comparing results of (tuned) ML-models and choosing one for sumbission. <br/><br/>
The *prophet.ipynb file contains only the prophet model which was optimized as much as possible to reduce RAM/CPU usage and redundancy to create a submission that would finish \<9h, unfortunateley as the [blog](https://www.lesterjones.nl/blog/3/optiver-trading-at-the-close) explains the submission test set did not suite the manner the Prophet model makes predictions the actual would be MAE on the test set remains a mystery.<br/><br/>

The rest of the content of this repo comes from the Kaggle competition that is downloaded a few steps below.

### Clone repo (recommended)
```bash 
    cd /path/to/your/directory/
    git clone https://github.com/LesterJones95/Optiver---Trading-At-The-Close-Introduction.git
```

### Get and save kaggle API token
In Kaggle: ```Profile > Settings > Generate New Token```  <br/>
In Windows add the file: C:\Users\<USER>\.kaggle.json
```json
    {
    "username": "<USERNAME>",
    "key": "<API_KEY>"
    }
``` 

# Create a virtual environment
- Create a virtual environment with Python 3.10
- Install the packages in requirements.txt in the virual environment

# Download dataset from Kaggle to your local machine
On local machine: 
```bash (run as Administor)
    # (In git-bash) You will need to "Run as Administrator" to install kaggle
    pip install kaggle
```
```bash
    # Download the dataset (5.15GB)
    export KAGGLE_API_TOKEN=<TOKEN>
    mkdir -p data && cd data
    kaggle competitions download -c optiver-trading-at-the-close

    # Extract the files and remove .zip
    unzip optiver-trading-at-the-close.zip && rm -rf optiver-trading-at-the-close.zip
    ls -Al


    # Get leaderboard [optional] 
    # Turns out the csv file does not have the scores
    # Would have been fun to calculate the average and see how these models compare.   
    kaggle competitions leaderboard -d --csv optiver-trading-at-the-close
    unzip optiver-trading-at-the-close.zip && rm -rf optiver-trading-at-the-close.zip
```

## Usage
In an IDE like Jupyter Notebook or Visual Studio Code this code should work when following the instructions above. <br/>

### PS
My personal set-up differs a little bit from this explanation above, it is however a little bit more complicated and requires more detailed instructions to set it up. <br/>
Instead of using a virtual environment I use Dockerfile and docker-compose to create a docker image that runs a jupyter-notebook with the correct configuration. To see an example of this, cehckout another of my project founds [here](https://github.com/LesterJones95/PetalsToTheMetal).

