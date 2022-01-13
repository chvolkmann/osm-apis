# osm-apis

A [docker-compose](https://docs.docker.com/compose/) setup for self-hosting OpenStreetMap services.

- [Nominatim](https://nominatim.org/https://wiki.openstreetmap.org/wiki/Nominatim), a geocoding API
- [Overpass](https://wiki.openstreetmap.org/wiki/Overpass_API), a querying API
- [Overpass Turbo](https://overpass-turbo.eu/), a web interface to Overpass




## Usage
Clone the repository
```bash
git clone https://github.com/chvolkmann/osm-apis
```

Edit `docker-compose.yml` and replace the URLs with your areas of interest. The default is set to *Hessen, Germany*.

Start the compose stack with

```bash
# add -d to daemonize
docker-compose up
```

This will start all containers, download and set up the databases from the respective PBF files and open ports according to the configuration.  Note that the first setup takes a while as the databases are decompressed and initialized.

The default port mapping is
- port 5060: Nominatim API
- port 5050: Overpass API
- port 5051: Overpass Turbo UI

Data will be persisted through Docker volumes in the local directory

```
osm-apis/
├── docker-compose.yml
├── nominatim-data/
└── overpass-data/
```