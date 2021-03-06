Libraries support
======================

.. _visualization:

Data visualization
--------------------
PyWebIO supports for data visualization with the third-party libraries.

Bokeh
^^^^^^^^^^^^^^^^^^^^^^

`Bokeh <https://github.com/bokeh/bokeh>`_ is an interactive visualization library for modern web browsers. It provides elegant, concise construction of versatile graphics, and affords high-performance interactivity over large or streaming datasets.

You can use ``bokeh.io.output_notebook(notebook_type='pywebio')`` in the PyWebIO session to setup Bokeh environment.
Then you can use ``bokeh.io.show()`` to output a boken chart::

    from bokeh.io import output_notebook
    from bokeh.io import show

    output_notebook(notebook_type='pywebio')
    fig = figure(...)
    ...
    show(fig)

See related demo on :charts_demo_host:`bokeh demo </?app=bokeh>`

In addition to creating ordinary charts, Bokeh can also build the Bokeh applications by starting the `Bokeh server <https://docs.bokeh.org/en/latest/docs/user_guide/server.html>`_. The purpose of the Bokeh server is to make it easy for Python users to create interactive web applications that can connect front-end UI events to real, running Python code.

In PyWebIO, you can also use ``bokeh.io.show()`` to display a Bokeh App. For the example, see `bokeh_app.py <https://github.com/wang0618/PyWebIO/blob/dev/demos/bokeh_app.py>`_.

.. note:: Bokeh App currently is only available in the default Tornado backend

.. image:: https://cdn.jsdelivr.net/gh/wang0618/pywebio-chart-gallery@master/assets/bokeh.png

pyecharts
^^^^^^^^^^^^^^^^^^^^^^

`pyecharts <https://github.com/pyecharts/pyecharts>`_  is a python plotting library which uses `Echarts <https://github.com/ecomfe/echarts>`_ as underlying implementation.

In PyWebIO, you can use the following code to output the pyecharts chart instance::

    # `chart` is pyecharts chart instance
    pywebio.output.put_html(chart.render_notebook())

See related demo on :charts_demo_host:`pyecharts demo </?app=pyecharts>`

.. only:: not latex

    .. image:: https://cdn.jsdelivr.net/gh/wang0618/pywebio-chart-gallery@master/assets/pyecharts.gif

plotly
^^^^^^^^^^^^^^^^^^^^^^

`plotly.py <https://github.com/plotly/plotly.py>`_ is an interactive, open-source, and browser-based graphing library for Python.

In PyWebIO, you can use the following code to output the plotly chart instance::

    # `fig` is plotly chart instance
    html = fig.to_html(include_plotlyjs="require", full_html=False)
    pywebio.output.put_html(html)

See related demo on :charts_demo_host:`plotly demo </?app=plotly>`

.. image:: https://cdn.jsdelivr.net/gh/wang0618/pywebio-chart-gallery@master/assets/plotly.png

cutecharts.py
^^^^^^^^^^^^^^^^^^^^^^

`cutecharts.py <https://github.com/cutecharts/cutecharts.py>`_ is a hand drawing style charts library for Python which uses `chart.xkcd <https://github.com/timqian/chart.xkcd>`_ as underlying implementation.

In PyWebIO, you can use the following code to output the cutecharts.py chart instance::

    # `chart` is cutecharts chart instance
    pywebio.output.put_html(chart.render_notebook())

See related demo on :charts_demo_host:`cutecharts demo </?app=cutecharts>`

.. image:: https://cdn.jsdelivr.net/gh/wang0618/pywebio-chart-gallery@master/assets/cutecharts.png
