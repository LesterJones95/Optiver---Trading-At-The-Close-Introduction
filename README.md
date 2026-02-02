# Kaggle 
This is the Kaggle challenge [Optiver - Trading at Close](https://www.kaggle.com/competitions/optiver-trading-at-the-close).
Done by me.

# Blog
Read my  [blog](https://www.lesterjones.nl/blog/3/optiver-trading-at-the-close) for a quick overview of the reason why this repository is made..

# Setup project 
### Clone repo (recommended)
```bash 
    cd /path/to/your/directory/
    git clone https://github.com/LesterJones95/Optiver---Trading-At-The-Close-Introduction.git
```

### Get and save kaggle API token
In Kaggle: ```Profile > Settings > Generate New Token```  <br/>

```bash
    cp kaggle-example.json kaggle.json
    # add your API Token and e-mail
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
```

## Usage
In an IDE like Jupyter Notebook or Visual Studio Code this code should work when following the instructions above. <br/>
