# Build Process Flow

Project build process works as follows:

1. Related structure graph is downloaded from Allen, eg. (http://api.brain-map.org/api/v2/structure_graph_download/8.json)[http://api.brain-map.org/api/v2/structure_graph_download/8.json]
2. Using the [LinkML-OWL](https://github.com/linkml/linkml-owl) structure graph is converted to the owl. [structure_graph_schema.yaml](https://github.com/hkir-dev/primate_brain_atlas_ontology/blob/main/src/linkml/structure_graph_schema.yaml) template is utilized for the conversion.
3. Related bridge files are downloaded from the [UBERON](https://github.com/obophenotype/uberon/tree/master/src/ontology/bridge) repo. In this case uberon-bridge-to-pba.obo and uberon-bridge-to-aba.obo
4. Using the [ROBOT](http://robot.obolibrary.org/) ontology templating tool, external links to the related atlas web pages are generated (linkouts.owl). Such as [http://atlas.brain-map.org/atlas?atlas=138322605#structure=10499](http://atlas.brain-map.org/atlas?atlas=138322605#structure=10499)
5. Finally all ontologies (linkouts.owl, structure graph ontology and bridges) are merged and the uberon import module added to the output ontology.