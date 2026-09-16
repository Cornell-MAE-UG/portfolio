---
layout: project
title: Analysis of Functions
description: Class project with Graphs
technologies:
  - MATLAB
  - Python
featured: false   # change to true to always show this project on your home page
image: /assets/images/function-graph.png
imagealt: Line plot titled "Analysis of Standard Functions" showing sin(x), cos(x) and 0.1*tan(x) for x from 0 to 10
---

> 📄 **Example page.** Replace all of it with your own project. The Latin text below is
> filler, here to show what a finished page looks like.

As part of a class project...Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut nec accumsan leo. Pellentesque ornare orci enim, vitae vestibulum nibh rutrum in. Donec pharetra risus nec ipsum fringilla, et mattis tortor auctor. Duis tortor ante, posuere ut odio a, scelerisque interdum purus. Pellentesque ornare orci enim, vitae vestibulum nibh rutrum in. Donec pharetra risus nec ipsum fringilla, et mattis tortor auctor. Duis tortor ante, posuere ut odio a, scelerisque interdum purus. Aenean faucibus luctus est, sed bibendum tellus. Nulla et magna urna. Morbi a ipsum sollicitudin, rhoncus risus volutpat, ultricies nunc. Quisque mollis finibus ante id imperdiet. Quisque vehicula elit sit amet felis facilisis fermentum.


Aenean faucibus luctus est, sed bibendum tellus. Nulla et magna urna. Morbi a ipsum sollicitudin, rhoncus risus volutpat, ultricies nunc. Quisque mollis finibus ante id imperdiet. Quisque vehicula elit sit amet felis facilisis fermentum.


This is how I solved the problem:

```python
  import numpy as np
  import matplotlib.pyplot as plt

  x = np.linspace(0, 10, 500)
  plt.plot(x, np.sin(x), label="sin(x)")
  plt.plot(x, np.cos(x), label="cos(x)")
  plt.legend()
```

Aenean tincidunt aliquam arcu, in euismod dui dapibus eu. In placerat, mi et ultrices consequat, quam ligula cursus mauris, in semper neque nibh at est. Maecenas hendrerit dignissim porta. Phasellus nec fringilla dolor. Etiam efficitur nisi sit amet velit pharetra feugiat. Etiam ultrices turpis at leo semper, eleifend scelerisque neque malesuada. Aliquam molestie congue rhoncus. Donec blandit neque dolor, nec tristique mi pretium ac. Mauris tincidunt ullamcorper magna, nec pellentesque mi sagittis quis.


