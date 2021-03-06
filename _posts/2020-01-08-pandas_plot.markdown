---
layout: post
title:      "Pandas .plot"
date:       2020-01-08 23:23:33 -0500
permalink:  pandas_plot
---


The pandas .plot method is a great tool to have.  It works with both Series and Data frames.  With a small amount of code, I can visualize data in a numerous amount of ways.  Scatter charts, histograms, bar charts, are all easily available and callable.  The scatter matrix is a great tool that shows any visible correlations between any of the columns.  It makes it simple to see if there is any columns that look interesting to investigate. 

The histogram is a great tool that helps you visualize how the data is spread and what kind of dispersion.  From first look, it is simple to see if there might be any outliers or problems with the data.  Without pandas, using matplotlib.pyplot gets heavy on the code.  Pandas .plot method reduces a lot of the code that is required in matplotlib.

Another great strategy to use with plots is to create a function that will handle some of the basic stuff to style the plot.  

```
def style_func(x,y, plot_title, x_title, y_title, fig_size):
    """
    Input:
    x: data for x axis
    y: data for y axis
    
    plot_title: title for plot
    
    x_title: label for x axis
    y_title: label for y_axis
    
    fig_size: tuple for figure size
    """
    
    plt.figure(figsize=fig_size)
    plt.scatter(x,y)
    
    plt.title(plot_title)
    
    plt.xlabel(x_title)
    plt.ylabel(y_title)
    
    return(plt.show())

```
