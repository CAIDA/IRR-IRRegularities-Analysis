# IRR-IRRegularities-Analysis

This repo contains the analysis code for the IMC2023 paper [IRRegularities in the Internet Routing Registry](https://www.caida.org/catalog/papers/2023_irregularities_in_internet_routing_registry/irregularities_in_internet_routing_registry.pdf).

## Results from paper
The file [radb_suspicious_6373.csv.gz](https://github.com/CAIDA/IRR-IRRegularities-Analysis/blob/main/radb_suspicious_6373.csv.gz) contains the 6,373 potentially suspicious records in RADB between November 2021 and May 2023.
The columns in the file are explained below:
- first column with no name: index
- prefix: BGP prefixes
- asn: BGP origin ASNs
- duration: number of seconds the prefix origin is observed in BGP
- route: prefix of the route object, same as prefix column
- origin: origin AS of the route object, same as asn column
- mnt-by: maintainer of the route object in RADB
- lifetime: number of days the route object is observed in RADB
- end_date: last-day the route object is observed in RADB. 2023-05-05 is the last day the RADB snapshot was retrieved.
- rpki_radb: RPKI consistency status of the RADB route object.
- radb_roas: corresponding ROAs of the RADB route objects, calculated using the ROV algorithm (RFC6811).

## Data requirements

You will need to download the following datasets.

- For [Parse_IRR_Dumps.ipynb](https://github.com/CAIDA/IRR-IRRegularities-Analysis/blob/main/Parse_IRR_Dump.ipynb): Download IRR snapshots from the IRR database providers. A list of current IRR database providers are listed here: https://www.irr.net/docs/list.html
- For [IRR_Inconsistency.ipynb](https://github.com/CAIDA/IRR-IRRegularities-Analysis/blob/main/IRR_Inconsistency.ipynb): Download the [CAIDA AS Organizations dataset](https://www.caida.org/catalog/datasets/as-organizations/) and the [CAIDA AS Relationship dataset](https://www.caida.org/catalog/datasets/as-relationships/)
- For [BGP_Overlap.ipynb](https://github.com/CAIDA/IRR-IRRegularities-Analysis/blob/main/BGP_Overlap.ipynb): Download the [CAIDA Routeviews Prefix2AS dataset](https://www.caida.org/catalog/datasets/routeviews-prefix2as/)

Sample proceessed datasets for 2024-01-01 are provided in the `data/` directory. Please refer to the links above for the latest datasets.

## Example result

### [IRR_Inconsistency.ipynb](https://github.com/CAIDA/IRR-IRRegularities-Analysis/blob/main/IRR_Inconsistency.ipynb):
The figure below shows the percentage of inconsistent IRR route objects between every 2 IRR databases.  

**Updated results from paper: As of 2024-01-01, authoritative IRRs no longer have inconsistencies with each other**

<img width="644" alt="Screenshot 2024-01-25 at 10 12 25 PM" src="https://github.com/CAIDA/IRR-IRRegularities-Analysis/assets/16662254/a010ebbc-49cd-490b-803d-c1bdee446595">  


### [BGP_Overlap.ipynb](https://github.com/CAIDA/IRR-IRRegularities-Analysis/blob/main/BGP_Overlap.ipynb)

The table below shows the fraction of overlapping prefix-origin pairs in IRR databases and BGP.

| IRR | Total prefix origin pairs in IRR | Percentage of overlapping prefix-origin pairs |
| :----- | -----: | -----: |
| afrinic | 110346 | 20.3% (22395/110346) |
| jpirr | 12976 | 66.55% (8636/12976) |
| canarie | 1424 | 54.99% (783/1424) |
| apnic | 694344 | 15.53% (107842/694344) |
| level3 | 74912 | 21.75% (16291/74912) |
| nestegg | 4 | 0.0% (0/4) |
| bboi | 840 | 42.26% (355/840) |
| idnic | 6078 | 59.3% (3604/6078) |
| wcgdb | 52035 | 6.03% (3137/52035) |
| tc | 21324 | 51.7% (11024/21324) |
| lacnic | 9739 | 66.91% (6516/9739) |
| ripe-nonauth | 51993 | 23.39% (12162/51993) |
| panix | 40 | 15.0% (6/40) |
| arin | 79146 | 57.12% (45211/79146) |
| radb | 1200188 | 27.91% (334963/1200188) |
| altdb | 24523 | 51.34% (12590/24523) |
| ripe | 406607 | 52.08% (211764/406607) |
| nttcom | 379455 | 13.76% (52203/379455) |
| bell | 29254 | 2.93% (857/29254) |

​
