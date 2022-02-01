To regenerate an OntoFox file like "general_import.owl" from command line rather than website (ontofox.hegroup.org)

curl -s -F file=@"general_ontofox.txt" -o general_import.owl http://ontofox.hegroup.org/service.php

To regenerate an owl file from a robot template, run this style of command:
NOTE: --input command ONLY ALLOWS ONE INPUT file; if you do multiple --input
only LAST one is used. Hence we need a merged version:

./robot.bat merge --input "../peston-edit.owl" --output peston-merged.owl

robot template --template robot_company.tsv \
  --input "peston-merged.owl" \
  --prefix "PESTON:http://purl.obolibrary.org/obo/PESTON_" \
  --ontology-iri "http://purl.obolibrary.org/obo/peston/imports/company_import.owl" \
  --output company_import.owl

./robot.bat template --template robot_pesticide.tsv \
  --input "peston-merged.owl" \
  --prefix "PESTON:http://purl.obolibrary.org/obo/PESTON_" \
  --ontology-iri "http://purl.obolibrary.org/obo/peston/imports/pesticide_import.owl" \
  --output pesticide_import.owl

./robot.bat template --template robot_active_ingredient.tsv \
  --input "peston-merged.owl" \
  --prefix "PESTON:http://purl.obolibrary.org/obo/PESTON_" \
  --ontology-iri "http://purl.obolibrary.org/obo/peston/imports/ai_import.owl" \
  --output ai_import.owl

./robot.bat template --template robot_address.tsv \
  --input "peston-merged.owl" \
  --prefix "PESTON:http://purl.obolibrary.org/obo/PESTON_" \
  --ontology-iri "http://purl.obolibrary.org/obo/peston/imports/address_import.owl" \
  --output address_import.owl

./robot.bat template --template robot_events.tsv \
  --input "peston-merged.owl" \
  --prefix "PESTON:http://purl.obolibrary.org/obo/PESTON_" \
  --ontology-iri "http://purl.obolibrary.org/obo/peston/imports/events_import.owl" \
  --output events_import.owl
