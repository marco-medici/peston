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

./robot.bat template --template robot_pesticide_authorization.tsv \
  --prefix "PESTON:http://purl.obolibrary.org/obo/PESTON_" \
  --ontology-iri "http://purl.obolibrary.org/obo/peston/imports/pesticide_authorization_import.owl" \
  --output pesticide_authorization_import.owl

./robot.bat template --template robot_ingredient.tsv \
  --input "peston-merged.owl" \
  --prefix "PESTON:http://purl.obolibrary.org/obo/PESTON_" \
  --ontology-iri "http://purl.obolibrary.org/obo/peston/imports/ingredient_import.owl" \
  --output ingredient_import.owl

./robot.bat template --template robot_ingredient_concentration.tsv \
  --input "peston-merged.owl" \
  --prefix "PESTON:http://purl.obolibrary.org/obo/PESTON_" \
  --prefix "UOM:https://w3id.org/uom/" \
  --ontology-iri "http://purl.obolibrary.org/obo/peston/imports/ingredient_concentration_import.owl" \
  --output ingredient_concentration_import.owl

./robot.bat template --template robot_address.tsv \
  --input "peston-merged.owl" \
  --prefix "PESTON:http://purl.obolibrary.org/obo/PESTON_" \
  --ontology-iri "http://purl.obolibrary.org/obo/peston/imports/address_import.owl" \
  --output address_import.owl

./robot.bat template --template robot_event.tsv \
  --input "peston-merged.owl" \
  --prefix "PESTON:http://purl.obolibrary.org/obo/PESTON_" \
  --ontology-iri "http://purl.obolibrary.org/obo/peston/imports/event_import.owl" \
  --output event_import.owl

./robot.bat template --template robot_pesticide_event.tsv \
  --prefix "PESTON:http://purl.obolibrary.org/obo/PESTON_" \
  --prefix "time:https://www.w3.org/TR/owl-time/#time:" \
  --ontology-iri "http://purl.obolibrary.org/obo/peston/imports/pesticide_event_import.owl" \
  --output pesticide_event_import.owl


