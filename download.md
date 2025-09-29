---
title:  Getting Started
layout: page
---

<style>

.download 
{
    background-color: white;
    border: 1px solid black;
    margin-left: 40px;
    min-width: 300px;
    padding: 10px;
    padding-left: 20px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    font-size: 18px;
    font-weight: 500;
    margin-bottom: -1px; /* Space between stacked boxes */
}

.download-grid {
    display: grid;
    grid-template-columns: auto auto auto auto; /* four natural-width columns */
    grid-auto-flow: row;
    margin-left: 40px;
    border: 1px solid black;
    border-collapse: collapse;
    background-color: white;
    width: fit-content;              /* ⬅ shrink to fit */
    max-width: 100%;                 /* optional safety */
}

.download-row {
    display: contents; /* let each .download-cell span grid columns */
    border-top: 1px solid black;
}

.download-row:first-of-type {
    border-top: none; /* remove top border for first row */
}

.download-cell {
    padding: 10px 14px 10px 14px;
    border-bottom: 1px solid black;
    font-size: 16px;
    display: flex;
    align-items: center;
}

.download-link {
    background-color: #388E3C; // #4CAF50; 
    color: white;
    cursor: pointer;
    text-decoration: none;
    padding: 8px 14px;
    font-size: 20px;
    border-radius: 5px;
    display: inline-block;
    transition: background-color 0.2s ease, box-shadow 0.2s ease;
}

.download-link:hover {
    text-decoration: none;
    background-color: #4CAF50; /* lighter green for glow */
    box-shadow: 0 0 5px rgba(76, 175, 80, 0.5);
}

.version-label {
    font-size: 10px;
    font-weight: 550;
    padding: 3px 3px 2px 3px;
    border-radius: 2px;
    text-transform: uppercase;
    line-height: 1;
    margin-left: 10px;
    vertical-align: 2px;
    letter-spacing: 0.06em;
}

.latest-label
{
    background-color: #4CAF50; /* green */
    color: white;
}

.beta-label
{
    background-color: #f0f000; /* yellow */
    color: black;
}

.platform-note {
    font-size: 10px;
    font-weight: 400;
    padding-left: 1px;
    padding-top: 2px;
}

.product-title
{
    font-family: "Fira Sans";
    font-size: 20px;
    font-weight: 400;
}

pre
{
background-color: rgb(39, 40, 34);
border-radius: 4px;
color: white;
padding: 6px 10px;
margin-bottom: 40px;
margin-left: 40px;
max-width: 440px; 
}

.highlight code
{
    color: white;  // TODO: use rouge
}

p
{
    margin-bottom: 12px;
}

.steps ul
{
	margin-top: 0px;
}

.steps li {
	font-size: 1.1em;
	color: #333333;
	font-weight: 300;
	line-height: 1.2em;
    margin-bottom: 8px;
}


</style>

<div class="text-container" markdown="1">

### GeoDesk gol CLI

Build and query Geo-Object Libraries (GOLs).


<div class="download-grid">
    <div class="download-row" data-platform="windows">
        <div class="download-cell product-title">gol CLI</div>
        <div class="download-cell">
            {{site.data.geodesk_gol_latest.version}}
            <span class="version-label latest-label">Latest</span> 
        </div>
        <div class="download-cell">Windows</div>
        <div class="download-cell">
            <a class="download-link" href="https://github.com/clarisma/geodesk-gol/releases/download/v{{site.data.geodesk_gol_latest.version}}/gol-{{site.data.geodesk_gol_latest.version}}-win-setup.exe">Download</a>
        </div>
    </div>
    <div class="download-row" data-platform="linux">
        <div class="download-cell product-title">gol CLI</div>
        <div class="download-cell">
            {{site.data.geodesk_gol_latest.version}}
            <span class="version-label latest-label">Latest</span>
        </div>
        <div class="download-cell">Linux</div>
        <div class="download-cell">
            <a class="download-link" href="https://github.com/clarisma/geodesk-gol/releases/download/v{{site.data.geodesk_gol_latest.version}}/gol-{{site.data.geodesk_gol_latest.version}}-linux.zip">Download</a>
        </div>
    </div>
    <div class="download-row" data-platform="macos">
        <div class="download-cell product-title">gol CLI</div>
        <div class="download-cell">
            {{site.data.geodesk_gol_latest.version}}
            <span class="version-label latest-label">Latest</span>
        </div>
        <div class="download-cell">macOS</div>
        <div class="download-cell">
            <a class="download-link" href="https://github.com/clarisma/geodesk-gol/releases/download/v{{site.data.geodesk_gol_latest.version}}/gol-{{site.data.geodesk_gol_latest.version}}-macos.zip">Download</a>
        </div>
    </div>
    <div class="download-row">
        <div class="download-cell product-title">gol CLI</div>
        <div class="download-cell">
            {{site.data.geodesk_gol_v1_latest.version}} <!-- <span class="version-label latest-label">Latest</span> -->
        </div>
        <div class="download-cell">
        <div>Multi-Platform<div class="platform-note">Requires Java 16+</div></div>
        </div>
        <div class="download-cell">
            <a class="download-link" href="https://github.com/clarisma/gol-tool/releases/download/{{site.data.geodesk_gol_v1_latest.version}}/gol-tool-{{site.data.geodesk_gol_v1_latest.version}}.zip">Download</a>
        </div>
    </div>
</div>

**Install:**

<div class="steps" markdown="1">
- Unzip in a location of your choice
- Add `gol` to your path (optional)
- *For gol {{site.data.geodesk_gol_v1_latest.version}} only:* [Install Java](https://adoptium.net/) (version 16 or above)
</div>

**Use:** ([Documentation](https://docs.geodesk.com/gol))

```bash
$ gol build france france-latest.osm.pbf
$ gol query france na[amenity=restaurant]
```

### GeoDesk for Python

Analyze and visualize OpenStreetMap data.<br> 
[Documentation](https://docs.geodesk.com/python) • [GitHub](https://github.com/clarisma/geodesk-py) 

```bash
$ pip install geodesk
```

### GeoDesk for Java

Build sophisticated geospatial applications.<br> 
[Tutorial](https://docs.geodesk.com/java) • [Javadoc](https://apidocs.geodesk.com/v2/) • [GitHub](https://github.com/clarisma/geodesk)  

{% include maven.md %}


### GeoDesk for C++

Our most powerful OpenStreetMap Toolkit.<br>[Tutorial](https://docs.geodesk.com/cpp) • [API Documentation](https://cppdoc.geodesk.com/) • [GitHub](https://github.com/clarisma/libgeodesk) 

```cmake
include(FetchContent)
FetchContent_Declare(geodesk GIT_REPOSITORY 
    https://github.com/clarisma/libgeodesk.git
    GIT_TAG main)
FetchContent_MakeAvailable(geodesk)
```

</div>