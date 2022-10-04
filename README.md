# LSST_Supernova_simulations
This GitHub intends to provide guide about the access management in the LSST project to the public, and supply information about its structure. This is one of the differents challenges when one faces to access to the properly data in the Rubin Science Platform and LSST DESC Data Portal. We particularly focus on testing the photometry of the Vera Rubin Telescope for simulated supernovas data at LSST DC2.

For this reason is very important to read the "Report of access of simulated supernovas data at LSST DC2" to understand the procedure to find the correct files that you will need for the simulation. However, the most important thing to keep in mind is the following information about the GCRCatalogs and where to find them:

## GCRCatalogs
GCRCatalogs is a Python package that serves as a repository of various galaxy catalogs and sky catalogs for the LSST Dark Energy Science Collaboration (DESC). It provides a unified user interface to access all catalogs by using the Generic Catalog Reader (GCR) base class (https://github.com/LSSTDESC/gcr-catalogs). 

The LSST DESC Data Portal allows all users to transfer the DC2 Public Release data using Globus Connect. In this web,  we had to create a GlobusID and set up the Globus Personal Connect in a local machine to download the files we will use. In the “FILE MANAGER” option, we had to search the catalogs:

* lsstdesc-public/dc2/run2.2i-dr6-v4/truth_sn/truth_sn_summary_v1-0-0.parquet
* lsstdesc-public/dc2/run2.2i-dr6-v4/truth_sn/truth_sn_variability_v1-0-0.parquet

Those files contain many information, and for this reason ,you should select only the data that you will use to avoid download extremely heavy files. Once the above has been done, we proceed to transfer those files to a local machine with the “Transfer” option and then, select the location in the local machine that we wanted.

Finally in Python, we loaded the supernova summary table, but Python didn’t recognize the files that we called. So, we realize that we had to organize the files like the file path shown in the repository:

(lsstdesc-public/dc2/run2.2i-dr6-v4/truth_sn/truth_sn_summary_v1-0-0.parquet, lsstdesc-public/dc2/run2.2i-dr6-v4/truth_sn/truth_sn_variability_v1-0-0.parquet).

Once those steps were finished, we could start working on the supernovas code.

