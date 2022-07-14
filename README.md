This repository is a fork of the [Pyodide Javascript Package](https://www.npmjs.com/package/pyodide). 

Our Seeq application project pulls this in as a `node_modules` dependency. We need this fork for a simple reason: we want to have strict control over which Python packages (wheels) are included in the `pyodide` distribution we use at runtime. 

The original package on `npm` contains a lot of additional Python wheels we do not have a use for and, hence, want to prevent from being accessed at runtime. So in this repository, we have removed all of these unnecessary wheels. We also have included two additional packages (`plotly` and `tenacity`) that are not included in the original `pyodide` distribution.

These are the Python Packages included, with notes regarding why they are included.

| Name				|Version| Description																			|Notes                              |
|-------------------|-------|---------------------------------------------------------------------------------------|-----------------------------------|
|bokeh				| 2.4.2	| Interactive plots and applications in the browser from Python							| Used by the Visualization Add-on	|
|distlib			| 0.3.1	| Distribution utilities																| Used by other libraries			|
|html5lib			| 1.1	| HTML parser based on the WHATWG HTML specification									| Nice for rendering				| 
|Jinja2				| 3.0.3	| A small but fast and easy to use stand-alone template engine written in pure python.	| bokeh depends on it				| 
|MarkupSafe			| 2.0.1	| Safely add untrusted strings to HTML/XML markup.										| Used by other libraries			| 
|micropip			| 0.1	| Pyodide package manager																| Part of Pyodide core				| 
|numpy				| 1.21.4| NumPy is the fundamental package for array computing with Python.						| Useful for data handling			| 
|packaging			| 21.3	| Core utilities for Python packages													| bokeh depends on it				| 
|pillow				| 9.0.0	| Python Imaging Library (Fork)															| bokeh depends on it				| 
|plotly				| 5.9.0	| An open-source, interactive data visualization library for Python						| Used by the Visualization Add-on	| 
|pyodide-interrupts	| 0.1.1	| Interrupt handling for pyodide.														| Part of Pyodide core				| 
|pyparsing			| 3.0.6	| Python parsing module																	| Used by other libraries			| 
|python-dateutil	| 2.8.2	| Extensions to the standard Python datetime module										| Part of Pyodide core				| 
|pytz				| 2021.3| World timezone definitions, modern and historical										| Used by other libraries			| 
|pyyaml				| 6		| YAML parser and emitter for Python													| bokeh depends on it				| 
|setuptools			| 60.3.1| Easily download, build, install, upgrade, and uninstall Python packages				| Used by other libraries			| 
|six				| 1.16.0| Python 2 and 3 compatibility utilities												| Used by other libraries			| 
|tenacity			| 8.0.1 | Retry code until it succeeds				                                            | plotly depends on it  			| 
|traits				| 6.3.2	| Observable typed attributes for Python classes										| May be used by other libraries	| 
|typing-extensions	| 4.0.1	| Backported and Experimental Type Hints for Python 3.6+								| bokeh depends on it				| 
