# IRR-IRRegularities-Analysis

This repo contains the analysis code for the IMC2023 paper [IRRegularities in the Internet Routing Registry](https://www.caida.org/catalog/papers/2023_irregularities_in_internet_routing_registry/irregularities_in_internet_routing_registry.pdf).

## Data requirements

You will need to download the following datasets.

- For [Parse_IRR_Dumps.ipynb](https://github.com/CAIDA/IRR-IRRegularities-Analysis/blob/main/Parse_IRR_Dump.ipynb): Download IRR snapshots from the IRR database providers. A list of current IRR database providers are listed here: https://www.irr.net/docs/list.html
- For [IRR_Inconsistency.ipynb](https://github.com/CAIDA/IRR-IRRegularities-Analysis/blob/main/IRR_Inconsistency.ipynb): Download the [CAIDA AS Organizations dataset](https://www.caida.org/catalog/datasets/as-organizations/) and the [CAIDA AS Relationship dataset](https://www.caida.org/catalog/datasets/as-relationships/)
- For [BGP_Overlap.ipynb]: Download the [CAIDA Routeviews Prefix2AS dataset](https://www.caida.org/catalog/datasets/routeviews-prefix2as/)

Sample proceessed datasets for 2024-01-01 are provided in the `data/` directory. Please refer to the links above for the latest datasets.

## Example result

Figure 1 shows the percentage of inconsistent IRR route objects between every 2 IRR databases.  

**Updated results from paper: Authoritative IRRs no longer have inconsistencies with each other**

<img width="644" alt="Screenshot 2024-01-25 at 10 12 25 PM" src="https://github.com/CAIDA/IRR-IRRegularities-Analysis/assets/16662254/a010ebbc-49cd-490b-803d-c1bdee446595">
Figure 1
