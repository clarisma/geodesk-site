---
date: 2023-11-07
title: GeoDesk for Python 0.1.4
categories:
  - releases
---

[GeoDesk for Python](https://docs.geodesk.com/python) Version 0.1.4 is now available.

- Large-area spatial queries are 4x to 30x faster. GeoDesk now finds the 60+ million mapped buildings in the U.S. in less than one second (10x 2.3GHz Xeon, 32 GB RAM, NVMe SSD)

- Area calculations for features near the polar regions are significantly more accurate (A scaling bug previously caused distortions of areas above 65 degrees latitude)

- Other fixes ([release notes](https://github.com/clarisma/geodesk-py/releases/tag/v0.1.4))

Install / upgrade: `pip install geodesk -U`

