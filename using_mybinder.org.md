# Mybinder.org

We used [mybinder.org](https://mybinder.org/) to to get a version of our jupyter notebooks directly to live.

You can start our main [notebook on LOSD](https://github.com/statistikstadtzuerich/documentation/blob/master/Linked_Data/Manual/LOSD_Manual_of_Statistik_Stadt_Zurich.ipynb) [here](https://mybinder.org/v2/gh/statistikstadtzuerich/documentation/master?filepath=Linked_Data%2FManual%2FLOSD_Manual_of_Statistik_Stadt_Zurich.ipynb)

## Configuring mybinder
All information is in the binder subfolder:
* Currently we only use environment.yml(https://github.com/statistikstadtzuerich/documentation/blob/master/binder/environment.yml) to include all relevant kernels (Sparql, R, python)
* postBuild could be used to add commands.

More information about possible configurations can be found [here](https://mybinder.readthedocs.io/en/latest/using.html#preparing-a-repository-for-binder)

## Important
It may take some time to start the notebook. Afterwards it can be directly used.

## Known Issues
* Not set to "trusted" yet.

## Licensing
This documentation is licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) ([Statistik Stadt Zürich](https://www.stadt-zuerich.ch/prd/de/index/ueber_das_departement/organisation/statistik_stadt_zuerich.html)).
