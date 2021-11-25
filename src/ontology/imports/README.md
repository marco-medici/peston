To regenerate an owl file from a robot template, run this style of command:
NOTE: --input command ONLY ALLOWS ONE INPUT file; if you do multiple --input
only LAST one is used.

robot template --template robot_company.tsv \
  --input "../peston-edit.owl" \
  --prefix "PESTON:http://purl.obolibrary.org/obo/PESTON_" \
  --ontology-iri "http://purl.obolibrary.org/obo/peston/imports/company_import.owl" \
  --output company_import.owl


robot template --template robot_pesticide.tsv \
  --input "../peston-edit.owl" \
  --prefix "PESTON:http://purl.obolibrary.org/obo/PESTON_" \
  --ontology-iri "http://purl.obolibrary.org/obo/peston/imports/pesticide_import.owl" \
  --output pesticide_import.owl
