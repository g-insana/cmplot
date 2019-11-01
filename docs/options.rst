Options
=======

The only mandatory arguments for cmplot are a dataframe containing the data and either a string or a list of strings which label the columns containing the discrete independent variables in the dataframe, as shown in the :doc:`quickstart` section.

Several additional optional arguments can be specified to customize the result, both in terms of content and of form.

.. option:: xcol

    a string or an array of strings, column name(s) of the dataframe that you wish to plot as "x".

    This should be the categorical independent variable. If more than one column name is given, the combination of these will be used as "x". See examples for interpretation. e.g. xcol="Species"

.. option:: ycol

    a string or an array of strings, column name(s) of the dataframe that you wish to plot as "y". Optional.

    These should be the continuous dependent variables. If ycol is not specified, then the function will plot all the columns of the dataframe except those specified in xcol.

    e.g. ycol=["Sepal.Length","Sepal.Width"] would plot sepals' length and width as a function of the flower species

.. option:: orientation

    'h' | 'v', default is 'h'

    Orientation of the plot (horizontal or vertical)

.. option:: xsuperimposed

    boolean, default is False

    The default behaviour is to plot each value of the categorical variable (or each combination of values for multiple categorical variables) in a separate position. Set to True to superimpose the plots. This is useful in combination with "side='alt'" to create asymmetrical plots and comparing combinations of categorical variables (e.g. Married + Gender ~ Wage).

.. option:: xlabel

    string or list of strings

    Override for labelling (and placing) the plots of the categorical variables. Only relevant when using xsuperimposed

.. option:: ylabel

    string or list of strings

    Override for labelling the dependent variables. If not specified, the labels for the dataframe ycol are used.

.. option:: title

    string

    If not specified, the plot title will be automatically created from the names of the variables plotted.

    e.g. title="Length of petals for the three species"

.. option:: side

    'pos' | 'neg' | 'both' | 'alt', default is 'alt'

    'pos' would create kernel density curves rising towards the positive end of the axis, 'neg' towards the negative, 'both' creates symmetric curves (like violin/bean/pirate plots). 'alt' will alternate between 'pos' and 'neg' in case where multiple ycol are plotted.

    e.g. side='both'

.. option:: altsidesflip

    boolean, default is False

    Set to True to flip the order of alternation between sides for the kernel density curves. Only relevant when side='alt'

.. option:: ycolorgroups

    boolean, default is True

    Set to False to have the function assign a separate colour when plotting different values of the categorical variable. Leave as True if all should be coloured the same.

.. option:: spanmode

    'soft' | 'hard', default is 'soft'

    Controls the rounding of the kernel density curves or their sharp drop at their extremities. With 'hard' the span goes from the sample's minimum to its maximum value and no further.

.. option:: pointsoverdens

    boolean, default is False

    Set to True to plot the raw data points over the kernel density curves. This is obviously the case when side='both', but otherwise by default points are plotted on the opposite side.

.. option:: showpoints

    boolean, default is True

    Set to False to avoid plotting the :term:`cloud` of data points

.. option:: pointsopacity

    float, range 0-1, default is 0.4

    The default is to plot the data points at 40% opacity. 1 would make points completely opaque and 0 completely transparent (in that case you'd be better served by setting showpoints to False).

.. option:: inf

    'hdi' | 'ci' | 'iqr' | 'none', default is 'hdi'

    To select the method to use for calculating the confidence interval for the inference :term:`band` around the mean. 'hdi' for Bayesian Highest Density Interval, 'ci' for Confidence Interval based on Student's T, 'iqr' for Inter Quantile Range. Use 'none' to avoid plotting the inference band.

.. option:: conf_level

    float, range 0-1, default is 0.95

    Confidence level to use when inf='ci', credible mass for inf='hdi'

.. option:: hdi_iter

    integer, default is 10000

    Iterations to use when performing Bayesian t-test when inf='hdi'

.. option:: showboxplot

    boolean, default is True

    Set to False to avoid displaying the mini :term:`boxplot`

.. option:: markoutliers

    boolean, default is True

    Set to False to avoid marking the :term:`outliers`

.. option:: pointshapes

    array of strings

    You can specify manually which symbols to use for each distribution plotted. If not specified, a random symbol is chosen for each distribution.

.. option:: pointsdistance

    float, range 0-1, default is 0.6

    Distance at which data points will be plotted, measured from the base of the density curve. 0 is at the base, 1 is at the top.

.. option:: pointsmaxdisplayed

    integer, default is 0

    This option sets the maximum number of points to be drawn on the graph. The default value '0' corresponds to no limit (plot all points). This option can be useful when the data amount is massive and would prove inefficient or inelegant to plot.

.. option:: colorrange

    integer, default is None

    By default, the distribution will be coloured independently, with the colours automatically chosen as needed for a single plot, maximising the difference in hue across the colour spectrum. You can override this by specifying a number to accomodate. This is useful when joining different plots together. E.g. if the total number of colours to be accomodating, after joining two plots, would equal 4, then set colorrange=4

.. option:: colorshift

    integer, default is 0

    This option is used in combination with colorrange to skip a certain amount of colours when they are to be assigned to the distributions to be plotted. This is useful when joining different plots together, to avoid having distributions plotted with the same colour.
