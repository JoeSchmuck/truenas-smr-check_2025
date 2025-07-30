# Forked from BasilHendroff
This script had not been updated since 2020 so I took it upon myselft to update a fork of this script.
The original author deserves credit for the original work done.

# truenas-smr-check
The script doesn't limit checks just to the WD NAS range of drives (RED), but extends this to any WD SMR drive listed in its database (BLUE, BLACK, Ultrastar, etc.). 

## Version 2.0
The version number is also present in the actual script which is used by Multi-Report to check for any updates.

## Status
This script will work with FreeNAS 11.3 and greater, to include TrueNAS Core and TrueNAS SCALE.

## How to Use
Download the repository to a convenient directory on your TrueNAS system by changing to that directory and running `git clone https://github.com/JoeSchmuck/truenas-smr-check_2025/`. Then change into the newly created directory and run the script `./smr-check.sh`. The script should only take a few seconds to execute. The script is non-invasive and does not leave anything behind after it completes. If SMR drives are detected, the device name, drive model and serial number of each drive is displayed in a table e.g.
```

Known SMR drive(s) detected.

 Device |           Model |        Serial Number |
--------------------------------------------------
   ada0 |     ST8000VX008 |             xxxxxxxx |
   ada1 |    HDWL120EZSTA |         xxxxxxxxxxxx |
   ada3 |        WD30EFAX |     xxxxxxxxxxxxxxxx |
```
The script SMR database is updated whenever previously unidentified SMR drives surface. It's important therefore to always download and use the latest version of this script. 

## Scope
Western Digital, Seagate and Toshiba SMR drives are detected.

The database of known SMR drives has been compiled from the following primary sources:
 1. https://www.truenas.com/community/resources/list-of-known-smr-drives.141/
 2. https://nascompares.com/answer/list-of-wd-cmr-and-smr-hard-drives-hdd/
 3. https://hddscan.com/blog/2020/hdd-wd-smr.html
 4. https://www.seagate.com/files/www-content/datasheets/pdfs/skyhawk-3-5-hdd-DS1902-15M-2103US-en_US.pdf
 5. https://www.seagate.com/www-content/datasheets/pdfs/skyhawk-3-5-hdd-DS1902-15-2009GB-en_AS.pdf
 6. https://www.seagate.com/www-content/datasheets/pdfs/barracuda-2-5-DS1907-3-2005GB-en_AU.pdf
 7. https://gutendata.de/portfolio-item/how-to-shoose-hard-drive-introduction-in-magnetic-recording-technology-that-maybe-you-heard-on-pmr-cmr-and-epmr-smr-hamr-and-mamr-tdmr-and-bpmr/
 8. https://documents.westerndigital.com/content/dam/doc-library/en_us/assets/public/western-digital/product/data-center-drives/ultrastar-dc-hc600-series/data-sheet-ultrastar-dc-hc620.pdf 
 9. https://documents.westerndigital.com/content/dam/doc-library/en_us/assets/public/western-digital/product/data-center-drives/ultrastar-dc-hc600-series/data-sheet-ultrastar-dc-hc650.pdf
 10.  https://www.toshiba-storage.com/wp/wp-content/uploads/2017/08/TOSH_16046_P300_GB_30_11.pdf
 11.  https://www.seagate.com/products/enterprise-drives/exos/exos-m/

## Disclaimer
This script is useful for quickly identifying SMR drives registered in the SMR database within the script. While every endeavour has been made to include as many SMR drives as possible, be aware the SMR database may not be complete. Therefore, you're advised not to rely solely on this script, but to confirm using other methods that SMR drives are not being used in your TrueNAS server.

## Discover a new SMR drive?
Please reach out if you discover an SMR drive that is not on the list.  Please provide the Manufacture, Model Number, and if possible a link to a reference stating the drive is SMR (manufacturer preferred).
