Dataframe
=========

Cloudy mountain plots will be created from data contained in a dataframe.

What if you don't have a dataframe to start with?

Simply create one from scratch with few lines of code:

* In Python:

.. code-block:: python

    >>> import pandas #load the module

    >>> mydata={} #create an empty hash

    >>> mydata['Species']=["setosa", "setosa", .... "virginica"] #load data for categorical variable

    >>> mydata['PetalWidth']=[0.2, 0.2, .... 1.8] #load data for dependent variable(s)

    >>> df=pandas.DataFrame(mydata) #create the dataframe

* In Julia:

.. code-block:: julia

    julia> using DataFrames #load the module

    julia> df=DataFrame() #create empty dataframe

    julia> df.Species=["setosa", "setosa", .... "virginica"] #load data for categorical variable

    julia> df.PetalWidth=[0.2, 0.2, .... 1.8] #load data for dependent variable(s)


You can refer to the excellent `Pandas <https://pandas.pydata.org/pandas-docs/stable/>`_ (for Python) or `DataFrames <https://juliadata.github.io/DataFrames.jl/stable/>`_ (for Julia) online documentation for other ways to construct or modify your dataframe.
