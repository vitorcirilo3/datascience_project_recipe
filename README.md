# # Data science project recipe

_This project aims to provide a data science environment that is: isolated (docker), optimized (using docker best practices to minimize image size), organized (cookiecutter by drivendata) and with the basic packages and technologies for the development of the your project._

<p align="center">
  <img align="center" src="https://miro.medium.com/max/875/1*AhwtYGu-oweotEK-n7uTuA@2x.jpeg" width="350" >
</p>
<p align="center">
  <sub>image credits: miro.medium.com</sup>
</p>

&nbsp;

### Requirements:
-----------
 - Docker 20.10.14+

&nbsp;

### To start a new project
------------

First of all, let's pull the docker image

    docker pull vitorcirilo3/datascience-project-recipe:1.0


Now, you can run the docker image (replace the project name)

    docker run -d -it --name {{datascience_project_name}} vitorcirilo3/datascience-project-recipe:1.0


Inside the docker you will have the following structure:
```
├── root
│   ├── main              <- You are here now
│   ├── config.yaml       <- the file that you need modify
```

Access the docker container and modify the config.yaml with the information of your project
```
default_context:
    author_name: "author_name"
    email: "email_information@email.com"
    project_name: "project_name"
    description: "A short description of the project."
    python_interpreter: ["python3"],
    cookiecutters_dir: "/root/main/"
```

After that, enter in the "main" folder and execute:

    cookiecutter -c v2-unofficial https://github.com/vitorcirilo3/cookiecutter-datascience -f --no-input --config-file ../config.yaml

**Congratulations! You done!** :vulcan_salute:

&nbsp;

### The resulting directory structure
------------

The directory structure of your new project looks like this: 

```
├── LICENSE
├── Makefile           <- Makefile with commands like `make data` or `make train`
├── README.md          <- The top-level README for developers using this project.
├── data
│   ├── external       <- Data from third party sources.
│   ├── interim        <- Intermediate data that has been transformed.
│   ├── processed      <- The final, canonical data sets for modeling.
│   └── raw            <- The original, immutable data dump.
│
├── docs               <- A default Sphinx project; see sphinx-doc.org for details
│
├── models             <- Trained and serialized models, model predictions, or model summaries
│
├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
│                         the creator's initials, and a short `-` delimited description, e.g.
│                         `1.0-jqp-initial-data-exploration`.
│
├── references         <- Data dictionaries, manuals, and all other explanatory materials.
│
├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
│   └── figures        <- Generated graphics and figures to be used in reporting
│
├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
│                         generated with `pip freeze > requirements.txt`
│
├── setup.py           <- makes project pip installable (pip install -e .) so src can be imported
├── src                <- Source code for use in this project.
│   ├── __init__.py    <- Makes src a Python module
│   │
│   ├── data           <- Scripts to download or generate data
│   │   └── make_dataset.py
│   │
│   ├── features       <- Scripts to turn raw data into features for modeling
│   │   └── build_features.py
│   │
│   ├── models         <- Scripts to train models and then use trained models to make
│   │   │                 predictions
│   │   ├── predict_model.py
│   │   └── train_model.py
│   │
│   └── visualization  <- Scripts to create exploratory and results oriented visualizations
│       └── visualize.py
│
└── tox.ini            <- tox file with settings for running tox; see tox.readthedocs.io
```


### References
------------
docker: https://www.docker.com/

drivendata: http://drivendata.github.io/cookiecutter-data-science/
