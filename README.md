#py_perceptabat
Python wrapper function for ACD perceptabat_cv with parallel processing support.

##Description
Calculates logP, logD, most acidic and basic apparent pKa and sigma using classic, GALAS or consensus algorithms.
Supports multithreading.
Results are returned as a dictioanry and are written to a CSV file.
No non-standard lib package dependencies.
Tested with Python 3.7.2.

##Example usage from CLI:
python py_perceptabat.py <input_filepath> <logD pH> <boolean for parallelization> <number of cores> <logP algorithm> <pKa alogrithm> <logD algorithms>
e.g. python py_perceptabat.py <input_filepath> 7.4 True 4 classic classic classic-classic

##Arguments
Set smiles_filepath to specify SMILES input file. The file must have two columns: SMILES and ID separated by a space;
Set logd_ph to define at which pH logD will be calculated;
Set parallel=True to enable parallelization using threading;
Set threads argument to specify the number of threads for parallelization. Inactive if parallel=False;
Set *_algo arguments to specify algorithm for each property prediction.
LogD predictions use logp and pka properties and algorithms for both respecitvely must be provided e.g. classic-galas. Please refer to ACD documentation for more details;
Set logp_train to specify .PCD training file for logP prediction.

NOTE: training from CLI is currently disabled.

## Authors
* This script was written by **Aretas Gaspariunas** (aretas.gaspariunas@lifearc.org or aretasgasp@gmail.com).