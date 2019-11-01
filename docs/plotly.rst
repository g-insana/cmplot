Plotly
======

The plotting function for cloudy mountain plots is built on top of the freely available `Plot.ly <https://plot.ly/>`_ graphic library.

You can refer to the excellent online documentation to modify the layout, create subplots, retouch the subtraces or directly modify the cloudy mountain plot source code to add your own features to it:

* `Python plotly documentation <https://plot.ly/python/>`_ and `figure reference <https://plot.ly/python/reference/>`_
* `Julia plotly documentation <http://spencerlyon.com/PlotlyJS.jl/>`_

Saving your plots
-----------------

Orca is used to export plot.ly plots as images (see `Static image export support <https://plot.ly/python/getting-started/#static-image-export-support>`_).

* In Python:

.. code-block:: python

    >>> p1=go.Figure(*cmplot(mydataframe,xcol="xsymbol"))
    >>> homedir = str(Path.home())+'/'
    >>> p1.write_image(homedir+'output_filename.pdf')

* In Julia:

.. code-block:: julia

    julia> using ORCA
    julia> p1=plot(cmplot(mydataframe,xcol=:xsymbol)...)
    julia> savefig(p1::Union{Plot,PlotlyJS.SyncPlot}, joinpath(homedir(),"output_filename.pdf"))

**Note**: You can simply use .svg or .png extension in the output_filename string in order to export the plot in svg or png format)*
