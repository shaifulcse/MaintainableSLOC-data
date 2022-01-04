# MaintainableSLOC-data


The `data/snaphot-info.txt` file contains: project name checkoutDate  and snapshot for checkout (first two columns). The last two columns contain similar information, but for building fanout information used in RQ3. 

### RQ1 and RQ2

The `data/metrics/change-metrics/` directory contains measurements for all the 49 Java projects. 
The first line (header) shows the metrics' names (columns are separated by tab). For each metric measurement, there can be multiple values because we captured the complete evolution history of each method. 

SLOCStandard values 5,6,7 means at the introduction (when the method was first pushed), the SLOCStandard was 5. Then after a change, it became 6, and then 7 (latest).   

But for change values (such as ChangeDates), the first value is always 0. It means the method was introduced that day. The first value is 0 for other indicators as well, because the method was introduced, not modified.  

### RQ3 

The `data/fanInfo/` directory contains measurements that were used for RQ3.

## Explanation of the headers:

MethodJson --- The json history file of the method of interest (this is to map with `data/metrics/change-metrics/`) 

MethodSignature --- Fully Qaulified Signature

FanInJsons     --- Json history files of methods that called the method of interest. NoCall means no one called. null means, we could not find the json history file for this caller method (The method existed two years ago, but does not exist now, as one of the reasons.)

FanInSignatures --- Qualified Signatures of the caller methods. 

Accurate? --- No means there is atleast one caller method that we could not resolve the fully qualified signature, so we don't have it's CodeShovel history (we will discard the complete row). 
 
DiscardDays --- We discard any change or bugs (e.g., revision, diff) upto this day, because in RQ3, we considered only the last two years from the current snapshot day.  

### RQ4 

The `data/metrics/quality-metrics/` directory contains measurements that were used for RQ4.
