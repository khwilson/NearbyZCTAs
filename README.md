# A collection of nearby ZCTAs

For example, for RDDs :)

## Contents

The main file of paired ZCTAs (ZIP Code Tabulation Areas) is `paired_zctas.csv.gz`. This is a two-column
CSV where if two (5-digit) ZCTAs are near each other they appear on the same row.

Note that if A and B are nearby, then both (A, B), (B, A), (A, A), and (B, B) *all* appear in the file.
Filter to your heart's content.

## Data sources

We use the work of John Goodall, who has done the hard work of merging *all* the ZCTAs from the Census
Bureau into a single file. The original source data is [here](https://github.com/jgoodall/us-maps).

For ease of use, we provide the ZCTA geojson as an LZMA compressed file in this repository as well.

## Method

We follow the steps to find nearby ZCTAs:
* Load the ZCTA geojson from Mr. Goodall's work
* Buffer each ZCTA by 0.01 degree longitude/latitude (approximately 1km)
* Find those buffered ZCTAs that overlap and print those pairs

## Requirements for Recreation

We use Python 3 in Jupyter notebooks. Full requirements (beyond Python 3) can be found in
`requirements.txt`

## License

The original source data is public domain. This repository is CC-BY 4.0.
