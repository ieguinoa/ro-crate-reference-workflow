# ro-crate-reference-workflow
Creating a RO-Crate package containing a reference workflow

This repo summarizes several steps required to obtain

## Current progress made:
 - CWL abstract is being formally defined in CWL (https://github.com/common-workflow-language/cwl-v1.2/pull/3)
 - A standalone tool was created to convert Galaxy workflow files (format 1 or 2) to CWL abstract (https://github.com/ieguinoa/cwl-from-galaxy). 
 - WIP to directly download the CWL abstract version of a workflow from Galaxy (https://github.com/ieguinoa/galaxy/tree/wf-export-cwl-abstract).
 
## TODO:
 - RO-Crate package SHOULD contain a human readable file describing what is contained in it. Ideally it would be a HTML page with a description and, in this particular case, an image describing the workflow. The options (not exclusive) are:
    - obtaining the graphic from cwltool (https://github.com/common-workflow-language/cwltool/tree/abstract-operation#visualizing-a-cwl-document) 
    - obtaining the graphic from Galaxy itself. This would involve implementing the download as it is not readily available.

 - Extend the creation of CWL-abstract from other WMS and workflow definition formats.  
