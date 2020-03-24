# ro-crate-reference-workflow
Creating a RO-Crate package containing a reference workflow

This repo summarizes several steps required to construct an RO-Create packaging a reference workflow and it's metadata. The expected results can be visualized in an example under example/galaxy_workflow which contains the files representing a workflow designed in Galaxy. This example is being "reviewed" at https://github.com/ResearchObject/ro-crate/issues/66

## Current progress made:
 - CWL abstract is being formally defined in CWL (https://github.com/common-workflow-language/cwl-v1.2/pull/3)
 - A standalone tool was created to convert Galaxy workflow files (format 1 or 2) to CWL abstract (https://github.com/ieguinoa/cwl-from-galaxy). 
 - WIP to directly download the CWL abstract version of a workflow from Galaxy (https://github.com/ieguinoa/galaxy/tree/wf-export-cwl-abstract). This branch is already accessible from a test public instance at (test.usegalaxy.be)[https://test.usegalaxy.be]. The URL to generate the CWL abstract of a workflow can be built like:
 https://test.usegalaxy.be/api/workflows/workflow_id/download?style=cwl_abstract  replacing workflow_id with the real id of the workflow. As stated before, this is work in progress so the output of this API call can change without notice.
 In all cases, the CWL abstract file can be valideted using the latest version of cwltool like:
 
 ```
 cwltool --enable-dev --validate abstract_cwl_file.cwl
 ```
 
 
## TODO:
 - Add DataCite attributes to the root metadata file. Current version of the specification does not define the way to include sufficient metadata to generate a DataCite citation (see https://researchobject.github.io/ro-crate/1.0/#direct-properties-of-the-root-data-entity).
 - Automatize the creation of the metadata files (ro-crate-metadata.jsonld,...) from Galaxy or any other WMS or Data Management software.
 - RO-Crate package SHOULD contain a human readable file describing what is contained in it. Ideally it would be a HTML page with a description and, in this particular case, an image describing the workflow. The options (not exclusive) are:
    - obtaining the graphic from cwltool (https://github.com/common-workflow-language/cwltool/tree/abstract-operation#visualizing-a-cwl-document) . This requires that the Operation class definition is merged. 
    - obtaining the graphic from Galaxy itself. This would require implementing the download as it is not readily available.

 - Extend the creation of CWL-abstract from other WMS and workflow definition formats.  
