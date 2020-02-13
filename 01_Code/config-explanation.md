## Config explanation
The following explains what each element of the config JSON file refers to

### Config_example
the config_example.json can be used as template for the config.json

### Locations

The following are locatons for saving files:

|Name|Description|
|---|---|
|epc_path|location of the EPC data|
|polygon_path|location of the polygon data|
|processing_path|location for saving files generated by the code|

### Required files

The following are data files that must be provided:

|Name|Description|Required columns|Location|Format|
|---|---|---|---|---|
|polygon_fname|Polygons for buildings|TOID, geometry|polygon_path|.geojson|
|lad_lookup_fname|Lookup between uprn and local authority|uprn, lad_lookup|polygon_path|.csv|
|building_height_fname|Height information for buildings|TOID, reH2, AbsHMax|polygon_path|.csv|
|uprn_lookup_fname|Lookup file between uprn and toid, used to join polygon features to other data|TOID, uprn|polygon_path|.csv|

### Generated files

The following are files generated by the code:

|Name|Description|Script|
|---|---|---|
|epc_output_fname|Combined EPC data for all UK certificates|01_Code/01_EPC/01_Import/01_import_data|
|epc_wales_fname|Wales only certificates|01_Code/01_EPC/02_Preprocessing/01_Sampling|
|epc_train_fname|Training set for Welsh certificates|01_Code/01_EPC/02_Preprocessing/01_Sampling|
|epc_test_fname|Test set for Welsh certificates|01_Code/01_EPC/02_Preprocessing/01_Sampling|
|epc_train_clean_fname|Clean training set|01_Code/01_EPC/02_Preprocessing/04_Categorical_cleanup|
|epc_test_clean_fname|Clean test set|01_Code/01_EPC/02_Preprocessing/04_Categorical_cleanup|
|epc_train_dd_fname|Data driven training feature set|01_Code/01_EPC/02_Preprocessing/06_data_driven_features|
|epc_test_dd_fname|Data driven test feature set|01_Code/01_EPC/02_Preprocessing/06_data_driven_features|
|epc_train_domain_fname|Domain driven training feature set|01_Code/01_EPC/02_Preprocessing/06_domain_driven_features|
|epc_test_domain_fname|Domain driven test feature set|01_Code/01_EPC/02_Preprocessing/06_domain_driven_features|
|epc_train_ex_fname|Exhaustive training feature set|01_Code/01_EPC/02_Preprocessing/06_exhaustive_features|
|epc_test_ex_fname|Exhaustive test feature set|01_Code/01_EPC/02_Preprocessing/06_exhaustive_features|
|buildings_fname||01_Code/02_EPC_proxies/Polygon_features|
|built_form_fname|Derived built form and block count|01_Code/02_EPC_proxies/Block_counts|
|polygon_features_fname|Features derived from the polygons such as area|01_Code/02_EPC_proxies/Polygon_features|