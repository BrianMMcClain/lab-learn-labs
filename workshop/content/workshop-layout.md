Workshops are made up of a collection of files:

- `workshop` - Directory under which your workshop files reside.
- `workshop/modules.yaml` - Configuration file with details of available modules which make up your workshop, and data variables for use in content.
- `workshop/workshop.yaml` - Configuration file which provides the name of the workshop, the list of active modules for the workshop, and any overrides for data variables.
- `workshop/content` - Directory under which your workshop content resides, including images to be displayed in the content.
- `resources` - Directory under which Kubernetes custom resources are stored for deploying the workshop using eduk8s.
- `resources/workshop.yaml` - The custom resources for eduk8s which describes your workshop and requirements it may have when being deployed.
- `resources/training-portal.yaml` - A sample custom resource for eduk8s for creating a training portal for the workshop, encompassing the workshop environment and a workshop instance.

Additionally, there are a few other files that go around building the workshop image:

- `Dockerfile` - Steps to build your workshop into an image ready for deployment. This would be left as is, unless you want to customize it to install additional system packages or tools.
- `kustomization.yaml` - A kustomize resource file for loading the workshop definition. When using this, the eduk8s operator still needs to have first been deployed.
- `.dockerignore` - List of files to ignore when building the workshop content into an image.
- `.eduk8signore` - List of files to ignore when downloading workshop content into the workshop environment at runtime.