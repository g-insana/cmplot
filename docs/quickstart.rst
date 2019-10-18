Quickstart
==========

* In Python:

.. code-block:: python

    >>> import plotly.graph_objects as go
    >>> from cmplot import cmplot

     #call the cmplot directly inside a plotly Figure function as:

    >>> go.Figure(*cmplot(mydataframe,xcol="xsymbol"))

     #alternatively get traces and layout as separate variables, so that you can modify them or combine with others before passing them to Figure() function:

    >>> (traces,layout)=(cmplot(mydataframe,xcol="xsymbol"))

     #[...] do something with traces/layout

    >>> go.Figure(traces,layout) #plot it

* In Julia:

.. code-block:: julia

    julia> using CMPlot

    julia> using PlotlyJS

    #call the cmplot directly inside a plotly Figure function as:

    julia> plot(cmplot(mydataframe,xcol=:xsymbol)...)

    #alternatively get traces and layout as separate variables, so that you can modify them or combine with others before passing them to Figure() function:

    julia> traces,layout=cmplot(mydataframe,xcol=:xsymbol)

    julia> # [...] do something with traces/layout

    julia> plot(traces,layout) # plot it

