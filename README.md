# brouter-web

Web client (by [@nrenner](https://github.com/nrenner) and [contributors](https://github.com/nrenner/brouter-web/graphs/contributors)) for the BRouter routing engine (by [@abrensch](https://github.com/abrensch)). _Work in progress_.

Instances:

-   [brouter.de/brouter-web](https://brouter.de/brouter-web/) _(provided by [@abrensch](https://github.com/abrensch))_
-   [brouter.damsy.net](https://brouter.damsy.net) _(provided by [@bagage](https://github.com/bagage))_

**This repository is only about the frontend**.
For the server/backend, BRouter routing engine, Android app, profiles, [brouter.de](https://brouter.de) site, see:  
https://github.com/abrensch/brouter

More information:  
https://brouter.de

## Contact

General BRouter discussions/questions, support:

-   [`#brouter` on IRC OFTC](https://webchat.oftc.net/?channels=#brouter). You can also use [Riot](https://riot.im/app/#/room/#_oftc_#brouter:matrix.org).
-   [Google Group](https://groups.google.com/group/osm-android-bikerouting)

## Translating

Translations are managed using the
[Transifex](https://www.transifex.com/openstreetmap/brouter-web/) platform. After
signing up, you can go to [BRouter's project
page](https://www.transifex.com/openstreetmap/brouter-web/dashboard/), select a language and
click **Translate** to start translating.

## Installation

As an alternative to the above online version, the standalone server of BRouter can also be run on your local desktop.

### Install BRouter (server with routing engine)

1.  download and unzip latest [BRouter revision](https://brouter.de/brouter/revisions.html)  
    e.g. for Linux (replace `~/opt/` with your preferred install directory and `1_4_11` with latest version):

            mkdir ~/opt/brouter
            cd ~/opt/brouter
            wget https://brouter.de/brouter_bin/brouter_1_4_11.zip
            unzip brouter_1_4_11.zip
            chmod +x ./standalone/server.sh

2.  download one or more [data file(s)](https://brouter.de/brouter/segments4/) (rd5) into `segments4` directory

### Install BRouter-Web (client)

1.  download BRouter-Web as subdirectory `brouter-web` of the `brouter` directory

    -   using the latest stable release - adjust to current version number - from
        https://github.com/nrenner/brouter-web/releases:

            wget https://github.com/nrenner/brouter-web/releases/download/0.7.0/brouter-web-0.7.0.zip
            unzip brouter-web-0.7.0.zip -d brouter-web

    -   OR the current development state (potentially instable and without runtime distributables):

            wget https://github.com/nrenner/brouter-web/archive/master.zip
            unzip master.zip
            mv brouter-web-master brouter-web

        -   build the distributable files required for runtime (only for development state), see section [Build](#build)

2.  copy `config.template.js` to `config.js`
3.  configure URL to `profiles2` directory  
    set `BR.conf.profilesUrl` in config.js, e.g. uncomment:

            BR.conf.profilesUrl = 'http://localhost:8000/profiles2/';

4.  add your API keys (optional)  
    copy `keys.template.js` to `keys.js` and edit to add your keys

### Run

1.  start BRouter server in the `standalone` directory with `./server.sh` or `server.cmd` (Windows)
2.  serve the `brouter` directory for BRouter-Web  
    This is needed for pre-loading the selected profile (unless you allowed local file access in the Browser). Depending on your setup (see [How to run things locally](https://threejs.org/docs/#manual/en/introduction/How-to-run-things-locally)), start a web server in the `brouter` directory, e.g.:

            python -m SimpleHTTPServer

3.  open http://localhost:8000/brouter-web/

## Build

### Dependencies

Requires [Node.js](https://nodejs.org/) and [Yarn](https://yarnpkg.com/en/).

### Install

    yarn

### Build

    yarn build #for release
    yarn build debug #for development

### Develop

    yarn serve

## License

Copyright (c) 2018 Norbert Renner and [contributors](https://github.com/nrenner/brouter-web/graphs/contributors), licensed under the [MIT License (MIT)](LICENSE)

## Credits and Licenses

-   [BRouter](https://github.com/abrensch/brouter) (not included)  
    by abrensch; [GNU General Public License, version 3.0 (GPLv3)](https://github.com/abrensch/brouter/blob/master/LICENSE)
-   [Leaflet](https://leafletjs.com/)  
    Copyright (c) 2010-2014, Vladimir Agafonkin; Copyright (c) 2010-2011, CloudMade; [2-clause BSD License](https://github.com/Leaflet/Leaflet/blob/master/LICENSE)
-   [leaflet-routing](https://github.com/Turistforeningen/leaflet-routing)  
    Copyright (c) 2013, Turistforeningen, Hans Kristian Flaatten. All rights reserved. [2-clause BSD License](https://github.com/Turistforeningen/leaflet-routing/blob/gh-pages/LICENSE)
-   [Leaflet.Elevation](https://github.com/MrMufflon/Leaflet.Elevation)  
    Copyright (c) 2013 Felix Bache; [MIT License](https://github.com/MrMufflon/Leaflet.Elevation/blob/master/LICENSE)
-   [D3.js](https://github.com/mbostock/d3)  
    Copyright (c) 2013, Michael Bostock. All rights reserved.; [3-clause BSD License](https://github.com/mbostock/d3/blob/master/LICENSE)
-   [Leaflet.Editable](https://github.com/Leaflet/Leaflet.Editable)  
    Yohan Boniface; WTFPL licence
-   [Leaflet Control Geocoder](https://github.com/perliedman/leaflet-control-geocoder)  
    Copyright (c) 2012 [sa3m](https://github.com/sa3m), Copyright (c) 2013 Per Liedman; [2-clause BSD License](https://github.com/perliedman/leaflet-control-geocoder/blob/master/LICENSE)
-   [leaflet-plugins](https://github.com/shramov/leaflet-plugins)  
    Copyright (c) 2011-2012, Pavel Shramov; [2-clause BSD License](https://github.com/shramov/leaflet-plugins/blob/master/LICENSE)
-   [Async.js](https://github.com/caolan/async)  
    Copyright (c) 2010-2014 Caolan McMahon; [MIT License](https://github.com/caolan/async/blob/master/LICENSE)
-   [Bootstrap](https://getbootstrap.com/)  
    Copyright (c) 2011-2014 Twitter, Inc; [MIT License](https://github.com/twbs/bootstrap/blob/master/LICENSE)
-   [jQuery](https://github.com/jquery/jquery)  
    Copyright 2005, 2014 jQuery Foundation and other contributors; [MIT License](https://github.com/jquery/jquery/blob/master/LICENSE.txt)
-   [DataTables](https://github.com/DataTables/DataTables)  
    Copyright (C) 2008-2014, SpryMedia Ltd.; [MIT License](https://www.datatables.net/license/MIT-LICENCE)
-   [Leaflet.EasyButton](https://github.com/CliffCloud/Leaflet.EasyButton)  
    Copyright (C) 2014 Daniel Montague; [MIT License](https://github.com/CliffCloud/Leaflet.EasyButton/blob/master/LICENSE)
-   [Bootbox](https://github.com/makeusabrew/bootbox)  
    Copyright (C) 2011-2014 by Nick Payne; [MIT License](https://github.com/makeusabrew/bootbox/blob/master/LICENSE.md)
-   [bootstrap-slider](https://github.com/seiyria/bootstrap-slider)  
    Copyright (c) 2015 Kyle Kemp, Rohit Kalkur, and contributors; [MIT License](https://github.com/seiyria/bootstrap-slider/blob/master/LICENSE.md)
-   [Leaflet.RestoreView](https://github.com/makinacorpus/Leaflet.RestoreView)  
    Copyright (c) 2012 Makina Corpus, [MIT License](https://github.com/makinacorpus/Leaflet.RestoreView/blob/master/LICENSE)
-   [Leaflet.Locate](https://github.com/domoritz/leaflet-locatecontrol)  
    Copyright (c) 2014 Dominik Moritz, [MIT License](https://github.com/domoritz/leaflet-locatecontrol/blob/gh-pages/LICENSE)
-   [Font Awesome](https://fontawesome.com/v4.7.0/license/)  
    by Dave Gandy; [SIL OFL 1.1](https://scripts.sil.org/OFL) (Font), MIT License (Code), CC BY 3.0 (Documentation)
-   [url-search-params](https://github.com/WebReflection/url-search-params)  
    Copyright (C) 2015-2017 Andrea Giammarchi - @WebReflection; [MIT License](https://github.com/WebReflection/url-search-params/blob/master/LICENSE.txt)
-   [bootstrap-select](https://github.com/snapappointments/bootstrap-select)  
    Copyright (c) 2012-2018 SnapAppointments, LLC; [MIT License](https://github.com/snapappointments/bootstrap-select/blob/v1.13.0-dev/LICENSE)
-   [leaflet-sidebar-v2](https://github.com/nickpeihl/leaflet-sidebar-v2)  
    Copyright (c) 2013 Tobias Bieniek; [MIT License](https://github.com/nickpeihl/leaflet-sidebar-v2/blob/master/LICENSE)
-   [CodeMirror](https://github.com/codemirror/CodeMirror)  
    Copyright (C) 2017 by Marijn Haverbeke <marijnh@gmail.com> and others; [MIT License](https://github.com/codemirror/CodeMirror/blob/master/LICENSE)
-   [Map BBCode](https://github.com/MapBBCode/mapbbcode)  
    Ilya Zverev; [Do What The F\*ck You Want To Public License](https://github.com/MapBBCode/mapbbcode/blob/master/LICENSE)
-   [Leafet.StravaSegments](https://gitlab.com/bagage/leaflet.stravasegments)  
    Copyright (c) 2018 Gautier Pelloux-Prayer; [MIT License](https://gitlab.com/bagage/leaflet.stravasegments/blob/master/LICENSE)
-   [polyline](https://github.com/mapbox/polyline)  
    Copyright (c), Development Seed; [BSD 3-Clause License](https://github.com/mapbox/polyline/blob/master/LICENSE)
-   [leaflet-fullHash](https://github.com/KoGor/leaflet-fullHash)  
    Copyright (c) 2014 KoGor; [MIT License](https://github.com/KoGor/leaflet-fullHash/blob/master/LICENSE)
-   [Turf.js](https://github.com/Turfjs/turf)  
    Copyright (c) 2019 Morgan Herlocker; [MIT License](https://github.com/Turfjs/turf/blob/master/LICENSE)
-   [i18next](https://github.com/i18next/i18next), [i18next-browser-languageDetector](https://github.com/i18next/i18next-browser-languageDetector), [i18next-xhr-backend](https://github.com/i18next/i18next-xhr-backend), [jquery-i18next](https://github.com/i18next/jquery-i18next/blob/master/LICENSE)  
    Copyright (c) 2017 i18next; [MIT License](https://github.com/i18next/i18next/blob/master/LICENSE)
-   [Leaflet TriangleMarker](https://github.com/themeler/leaflet-triangle-marker)  
    Copyright (c) 2018 Przemysław Melnarowicz; [MIT License](https://github.com/themeler/leaflet-triangle-marker/blob/master/LICENSE)
-   [jsTree ](https://github.com/vakata/jstree)  
    Copyright (c) 2014 Ivan Bozhanov; [MIT License](https://github.com/vakata/jstree/blob/master/LICENSE-MIT)
-   [Leaflet.snogylop](https://github.com/ebrelsford/leaflet.snogylop)  
    Copyright (c) 2014 Eric Brelsford; [MIT License](https://github.com/ebrelsford/Leaflet.snogylop/blob/master/LICENSE)
-   [JOSM maps](https://josm.openstreetmap.de/wiki/Maps)  
    imagery database is licensed under [CC-BY-SA](https://creativecommons.org/licenses/by-sa/3.0/)
-   [LayersCollection](https://github.com/Edward17/LayersCollection/tree/gh-pages)  
    Copyright (c) 2016 Eduard &lt;edward17&gt;; [MIT License](https://github.com/Edward17/LayersCollection/blob/gh-pages/LICENSE.md)
-   [Leaflet-providers](https://github.com/leaflet-extras/leaflet-providers)  
    Copyright (c) 2013 Leaflet Providers contributors All rights reserved.; [2-clause BSD License](https://github.com/leaflet-extras/leaflet-providers/blob/master/license.md)
-   [Fetch polyfill](https://github.com/Github/fetch)  
    Copyright (c) 2014-2016 GitHub, Inc.; [MIT License](https://github.com/github/fetch/blob/master/LICENSE)
-   [Promise Polyfill](https://github.com/taylorhakes/promise-polyfill)  
    Copyright (c) 2014 Taylor Hakes, Copyright (c) 2014 Forbes Lindesay; [MIT License](https://github.com/taylorhakes/promise-polyfill/blob/master/LICENSE)
-   [Leaflet.FileLayer](https://github.com/makinacorpus/Leaflet.FileLayer)  
    Copyright (c) 2012 Makina Corpus; [MIT License](https://github.com/makinacorpus/Leaflet.FileLayer/blob/master/LICENSE)
-   [togeojson](https://github.com/mapbox/togeojson)  
    Copyright (c) 2016 Mapbox All rights reserved.; [2-clause BSD License](https://github.com/mapbox/togeojson/blob/master/LICENSE)
-   [Leaflet.hotline](https://github.com/iosphere/Leaflet.hotline)  
    Copyright (c) 2015, iosphere GmbH, Jonas Coch; [Leaflet.hotline](https://github.com/iosphere/Leaflet.hotline/blob/master/LICENSE)
