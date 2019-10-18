Introduction
============

A Cloudy Mountain Plot is an informative RDI [#f1]_ `categorical distribution <https://en.wikipedia.org/wiki/Categorical_distribution>`_ plot inspired by Violin, Bean and Pirate Plots.

* Like `Violin plots <https://en.wikipedia.org/wiki/Violin_plot>`_, it shows smoothed kernel density curves, revealing information which would be hidden in boxplots, for example presence of multiple "peaks" ("modes") in the distribution "mountain".

* Like `Bean plots <https://www.jstatsoft.org/article/view/v028c01>`_, it shows the raw data, drawn as a cloud of points. By default all data points are shown but you can optionally control this and limit the display to a subset of the data.

* Like `Pirate plots <https://github.com/ndphillips/yarrr>`_, it marks confidence intervals (either from Student's T or as Bayesian Highest Density Intervals or as interquantile ranges) for the probable position of the true population mean.

Since by default it does not symmetrically mirror the density curves, it allows immediate comparisions of distributions side-by-side.

Elements of the plot
--------------------

.. figure:: img/cloudy_mountain_plot_elements.png
   :alt: elements of a cloudy mountain plot

.. glossary::

   cloud
      Marker symbols show the number and location of the raw data points.
      They are shown jittered for clarity.
      It is possible to fully control both the aspect (opacity and shape) of
      the markers and their number (in case showing them all would prove too slow or
      unelegant). It is also possible not to show any point.

   mountain
      `Kernel density estimation <https://en.wikipedia.org/wiki/Kernel_density_estimation>`_ curve.

   line
      Indicates the mean of the distribution

   band
      Probable position of the true population mean, to desired level of confidence.
      Method used can be specified as either CI [#f2]_ , HDI [#f3]_ or IQR [#f4]_.
      It is also possible not to show the band.
      

   boxplot
      A small `boxplot <https://en.wikipedia.org/wiki/Boxplot>`_. It can be shown
      or hidden, as desired.

   outliers
      The `outliers <https://en.wikipedia.org/wiki/Outlier>`_ are marked without
      jitter, on the baseline, and with less transparency. It is also possible not to
      show the outliers.

.. rubric:: Footnotes

.. [#f1] RDI: Raw data + Descriptive statistics + Inferential statistics
.. [#f2] CI: `Confidence Interval <https://en.wikipedia.org/wiki/Confidence_interval>`_, from Student's T distribution
.. [#f3] HDI: `Bayesian Highest Density Intervals <https://en.wikipedia.org/wiki/Credible_interval>`_
.. [#f4] IQR: `Interquartile range <https://en.wikipedia.org/wiki/IQR>`_
