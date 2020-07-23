# CT PPP Project

The CT PPP Project studies the Payment Protection Program (PPP) in Connecticut. The goals of this open data science initiative include:

* informing policy related to the PPP and other programs for Connecticut small business.
* helping Connecticut residents better understand the scope of PPP lending in the state.
* providing useful data and analysis that can assist other COVID-19-related research.
* supporting Connecticut journalists and local news organizations reporting on the PPP.

## Data

The data directory includes clean versions of the SBA-released datasets for loan
approvals through June 30, 2020. The SBA FOIA releases are also in the directory for reference. The new versions are in both JSON and CSV, and
include a composite dataset aggregating the \>$150K and \<$150K data. The differences between the two \>$150K and \<$150K datasets are: 1) the larger loans include both business names and addresses; and 2) larger loans do not provide exact dollar amounts but instead give dollar ranges.

Differences between the clean data and the original SBA data can be seen through the
JSON and CSV files in the audit directory. These files list the observations that have
been changed. To faciliate identification and comparison, a LoanID field was added to the clean datasets
using the indices in the original SBA datasets, prepended by the data tranche date 
and a two-letter indicator of the original SBA file.

Some loans were deleted from the SBA data because it was determined that the loans were incorrectly categorized. One larger loan was deleted:
Item 129047 in the national \>$150K dataset; and ten smaller loans were deleted: Items 963, 1173,
8317, 22015, 22210, 22881, 26843, 27730, 31801, and 52357 in the state \<$150K dataset. In
addition, three loans might have been intended as CT loans, but were listed by the SBA in other states; they
were also not included: Items 229534, 231108, and 259299 in the national \>$150K dataset.

Because the SBA-provided \<$150K dataset contained a large number of incorrect city names, zip
codes alone were used to identify their locations, unless all other data pointed to an out-of-state
loan. In New Haven/East Haven, although individual zip codes are shared by both cities, the
aggregate number and dollar amount of loans was nearly identical after using zip codes alone.


Because the SBA only provided dollar intervals for the larger loans, point estimates were often used for
ease of analysis and to illustrate aggregate dollar amounts. The point estimates in the initial summary report were made by
taking the same % of each interval for each of the loan ranges, such that the total loan amount
would equal the total amount reported by the SBA for Connecticut (after accounting for any deletions
made above). This percentage was computed to be 35.425%, and the resulting point estimates for
each of larger loan sizes were: $6,771,250 ($5M-$10M), $3,062,750 ($2M-$5M), $1,354,250 ($1M-
$2M), $580,262 ($350K-$1M), and $220,850 ($150K-$350K).

## Notebooks

Example Jupyter notebooks for analyzing the CT PPP data are in the notebook directory.
They can be run locally with a standard data science environment or by using Google
Colab. The notebooks assume the input files are in the current working directory.
Some geographic files needed to plot maps are found in the misc directory.

These notebooks give example code for loading data from the \>$150K, \<$150K, and composite JSON files for analysis; plotting graphs that illustrate static and dynamic variables in the CT PPP data; and creating maps that contain zip code-level information for Connecticut.

## Support

Please direct questions to ctppp.project@gmail.com.
