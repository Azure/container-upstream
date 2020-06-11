# Azure Container Compute Upstream

## Welcome
As the software development term ["Upstream"](https://en.wikipedia.org/wiki/Upstream_(software_development)) implies, the Azure Container Compute Upstream team is the team at Microsoft responsible for creating and leading the open source initiatives and projects related to container technologies and the [Kubernetes](https://kubernetes.io/) ecosystem. Our team is committed to working with the community, of both contributors and customers, to enhance the overall usabilty experience by helping to build and contribute to useful and valuable open source projects.

## Contents

* [Upstream Projects Overview](#upstream-projects-overview)
* [Upstream Project Announcements](#upstream-project-announcments)
* [Upstream Project Support](#upstream-projects-support)
* [Upstream Project List - Operating Personas](#upstream-project-list---operating-personas)
  * [Kubernetes Cluster Management](#kubernetes-cluster-management)
  * [Kubernetes Azure Cloud Provider](#kubernetes-azure-cloud-provider)
  * [Kubernetes Enhancements](#kubernetes-enhancements)
  * [Kubernetes Secure Infrastructure & Governance](#kubernetes-secure-infrastructure--governance)
  * [Kubernetes Service Mesh](#cloud-native-service-mesh)
  * [Container Runtime](#container-runtime)
* [Project Maturity](#project-maturity)
* [Contributing](#contributing)



## Upstream Projects Overview

When a particular technology gap is recognized in a common use case, or there is a need to enhance a user experience, the Azure Container Compute Upstream team will evaluate the opportunity to contribute a solution to the community. These community projects are maintained by the Azure Container Compute Upstream team. To see which of these projects may be useful to you, we have organized them to be aligned and/or categorized with an operating persona, so that we can focus a scope of functionality for the current and future project alignment. The list of projects is intended to help you make an informed decision about what projects you will consider n the context of your goals (e.g. proof of concept vs. production). To make this decision you will need to consider your goals, your need for formal support, the project's [maturity](#Maturity), governance, version level, and your willingness to consume and contribute to an open source project.

## Upstream Project Announcments
Here's where the Azure Container Compute Upstream team will communicate and highlight any new or current project announcments that you should be aware of.

| Date | Project | Announcement | Details |
|---|---|---|---|
|||No announcments at this time. Please check back soon.||

## Upstream Projects Support

It is extremely important, as well as crucial, to understand that the projects created and maintained by the Azure Container Compute Upstream team are 100% community based open source projects. These projects, much like other open source community projects, are considered out-of-tree plug-ins, meaning they are not inherently apart of the associated upstream project code repository and therefore have their own support mechanisms and deprecation lifecycle. Even though the core group of maintainers are Microsoft employees, projects listed on this page are [**NOT** covered by the Microsoft Azure support policy](https://support.microsoft.com/en-us/help/2941892/support-for-linux-and-open-source-technology-in-azure). To get help with these projects please search the open issues on the project using the links in the table. To communicate with the Azure Container Compute Upstream team please use the [issues](https://github.com/Azure/container-compute-upstream/issues) in this repo or the associated project repo's issues. If your issue isn't already represented, please open a new one. However, if you consume one of these projects as a part of a Microsoft or Azure product or service, you may be eligible for [support through that product or service](https://support.microsoft.com/en-us/hub/4343728/support-for-business).

## Upstream Project List - Operating Personas
To better focus and align our efforts, both internally and externally with the community, the Azure Container Compute Upstream team has categorized project work into key scenarios associated with an operating persona. We understand that some of the current and future projects may operate beyond thier category as well as operate in multiple categories. We have attempted to associate the projects in the following personas. We would like to hear any feedback if you feel that the projects are wrongly categorized or more category distinction should be added to the list.

### Kubernetes Cluster Management

| Project & (artifacts) | Goal | Project State & <br> API Version | Communication | Use on Azure |
|---|---|---|---|---|
| [AKS Engine](https://github.com/Azure/aks-engine) <br> ([releases](https://github.com/Azure/aks-engine/releases)) | Self-managed clusters on Azure | Azure: incubating <br> API: N/A | [#aks-engine-users](https://kubernetes.slack.com/archives/CU3N85WJK) <br> [GitHub issues](https://github.com/Azure/aks-engine/issues) | <ul><li>[Azure Kubernetes Service](https://docs.microsoft.com/en-us/azure/aks/)</li><li>[Azure Stack Hub](https://docs.microsoft.com/en-us/azure-stack/user/azure-stack-kubernetes-aks-engine-overview)</li></ul> |
| [Cluster API Azure Provider](https://sigs.k8s.io/cluster-api-provider-azure) <br> ([releases](https://github.com/kubernetes-sigs/cluster-api-provider-azure/releases)) <br> [Tests](https://testgrid.k8s.io/sig-cluster-lifecycle-cluster-api-provider-azure) | Self-managed clusters on Azure using Cluster API | CNCF: incubating <br> API: v1alpha3 | [#cluster-api-azure](https://kubernetes.slack.com/archives/CEX9HENG7) <br> [kubernetes-sig-cluster-lifecycle@googlegroups.com](https://groups.google.com/forum/#!forum/kubernetes-sig-cluster-lifecycle) <br> [GitHub issues](https://github.com/kubernetes-sigs/cluster-api-provider-azure/issues) |  |

### Kubernetes Azure Cloud Provider

| Project & (artifacts) | Goal | Project State & <br> API Version | Communication | Use on Azure |
|---|---|---|---|---|
| [In-tree (legacy)](https://github.com/kubernetes/kubernetes/tree/master/staging/src/k8s.io/legacy-cloud-providers/azure) <br> ([releases](https://github.com/kubernetes/kubernetes/releases)) <br> [Tests](https://testgrid.k8s.io/provider-azure-upstream) | Use Azure infra for K8s | CNCF: graduated <br> API: stable | [#provider-azure](https://kubernetes.slack.com/archives/C5HJXTT9Q) <br> [kubernetes-provider-azure@googlegroups.com](https://groups.google.com/forum/#!forum/kubernetes-provider-azure) <br> [GitHub issues](https://github.com/kubernetes/kubernetes/issues?q=is%3Aissue+is%3Aopen+label%3Aarea%2Fprovider%2Fazure+) | <ul><li>[Azure Kubernetes Service](https://docs.microsoft.com/en-us/azure/aks/)</li><li>[Use with AKS Engine](https://github.com/Azure/aks-engine)</li></ul> |
| [Cluster Autoscaler Azure Provider](https://github.com/kubernetes/autoscaler/tree/master/cluster-autoscaler/cloudprovider/azure) <br> ([releases](https://github.com/kubernetes/autoscaler/blob/master/cluster-autoscaler/README.md#releases)) <br> [Tests](https://testgrid.k8s.io/provider-azure-cloud-provider-azure#cloud-provider-azure-autoscaling) | Use cluster data to scale out/back nodes | CNCF: N/A <br> API: stable | same slack and email <br> [GitHub issues](https://github.com/kubernetes-sigs/cloud-provider-azure/issues) | <ul><li>[Azure Kubernetes Service](https://docs.microsoft.com/en-us/azure/aks/cluster-autoscaler)</li><li>[Use with AKS Engine](https://github.com/Azure/aks-engine/tree/master/examples/addons/cluster-autoscaler)</li></ul> |
| [Out-of-tree Provider](https://sigs.k8s.io/cloud-provider-azure) <br> ([releases](https://github.com/kubernetes-sigs/cloud-provider-azure/releases)) <br> [Tests](https://testgrid.k8s.io/provider-azure-cloud-provider-azure) | Use Azure infra for K8s | CNCF: N/A <br> API: alpha | same slack and email <br> [GitHub issues](https://github.com/kubernetes-sigs/cloud-provider-azure/issues) | [Use with AKS Engine](https://github.com/kubernetes-sigs/cloud-provider-azure/blob/master/docs/cloud-controller-manager.md) |
| [Azure Disk CSI Driver](https://sigs.k8s.io/azuredisk-csi-driver) <br> ([releases](https://github.com/kubernetes-sigs/azuredisk-csi-driver/releases)) <br> [Tests](https://testgrid.k8s.io/provider-azure-azuredisk-csi-driver)  | Enable use of Azure disk volume | CNCF: N/A <br> API: N/A | same slack and email <br> [GitHub issues](https://github.com/kubernetes-sigs/azuredisk-csi-driver/issues) | [Use with AKS Engine](https://github.com/kubernetes-sigs/cloud-provider-azure/blob/master/docs/cloud-controller-manager.md) |
| [Azure File CSI Driver](https://sigs.k8s.io/azurefile-csi-driver) <br> ([releases](https://github.com/kubernetes-sigs/azurefile-csi-driver/releases)) <br> [Tests](https://testgrid.k8s.io/provider-azure-azurefile-csi-driver) | Enable use of Azure disk volume | CNCF: N/A <br> API: N/A | same slack and email <br> [GitHub issues](https://sigs.k8s.io/azurefile-csi-driver/issues) | [Use with AKS Engine](https://github.com/kubernetes-sigs/cloud-provider-azure/blob/master/docs/cloud-controller-manager.md) |
| [Azure Blobfuse CSI Driver](https://sigs.k8s.io/blobfuse-csi-driver) <br> ([releases](https://github.com/kubernetes-sigs/blobfuse-csi-driver/releases)) <br> [Tests](https://testgrid.k8s.io/provider-azure-blobfuse-csi-driver) | Enable use of [azure-storage-fuse](https://github.com/Azure/azure-storage-fuse) | CNCF: N/A <br> API: N/A | same slack and email <br> [GitHub issues](https://github.com/kubernetes-sigs/blobfuse-csi-driver/issues) |  |

### Kubernetes Enhancements

| Project & (artifacts) | Goal | Project State & <br> API Version | Communication | Use on Azure |
|---|---|---|---|---|
| [Virtual Kubelet](https://github.com/virtual-kubelet/virtual-kubelet/) <br> ([releases](https://github.com/virtual-kubelet/virtual-kubelet/releases)) | Enable services to masquerade as kubelet - serverless | CNCF: sandbox <br> API: N/A | [#virtual-kubelet](https://kubernetes.slack.com/archives/C8YU1QP8W) <br> [GitHub issues](https://github.com/virtual-kubelet/virtual-kubelet/issues) | [AKS Virtual Nodes](https://docs.microsoft.com/en-us/azure/aks/virtual-nodes-cli) |
| [Windows containers](https://kubernetes.io/docs/setup/production-environment/windows/intro-windows-in-kubernetes/) <br> ([kubernetes releases](https://github.com/kubernetes/kubernetes/releases)) <br> [Tests](https://testgrid.k8s.io/sig-windows#aks-engine-azure-1-17-windows) | Run Windows server containers with Kubernetes | CNCF: stable <br> API: N/A | [#sig-windows](https://kubernetes.slack.com/archives/C0SJ4AFB7) <br> [kubernetes-sig-windows@googlegroups.com](https://groups.google.com/forum/#!forum/kubernetes-sig-windows) <br> [Windows Community Forum](https://discuss.kubernetes.io/c/general-discussions/windows) <br> [GitHub issues](https://github.com/kubernetes/kubernetes/issues?q=is%3Aissue+is%3Aopen+label%3Asig%2Fwindows+) | <ul><li>[AKS Windows](https://docs.microsoft.com/en-us/azure/aks/windows-container-cli)</li><li>[AKS Engine Windows](https://github.com/Azure/aks-engine/blob/master/docs/topics/windows.md)</li></ul> |
| [IPv4/v6 Dual Stack](https://kubernetes.io/docs/concepts/services-networking/dual-stack/) <br> ([kubernetes releases](https://github.com/kubernetes/kubernetes/releases)) <br> [Tests](https://testgrid.k8s.io/provider-azure-dualstack) | IPv4/IPv6 dual-stack enables the allocation of both IPv4 and IPv6 addresses to Pods and Services. | CNCF: stable <br> Feature: alpha | [#sig-network](https://kubernetes.slack.com/archives/C09QYUH5W) <br> [kubernetes-sig-network@googlegroups.com](https://groups.google.com/forum/#!forum/kubernetes-sig-network) <br> [GitHub issues](https://github.com/kubernetes/kubernetes/labels/area%2Fipv6) | [Use with AKS Engine](https://github.com/Azure/aks-engine/tree/master/examples/dualstack) |

### Kubernetes Secure Infrastructure & Governance

| Project & (artifacts) | Goal | Project State & <br> API Version | Communication | Use on Azure |
|---|---|---|---|---|
| [AAD Pod Identity](https://github.com/Azure/aad-pod-identity) <br> ([releases](https://github.com/Azure/aad-pod-identity/releases)) | Enables K8s applications to access cloud resources securely with Azure Active Directory | Azure: incubation <br> API: v1 | [GitHub issues](https://github.com/Azure/aad-pod-identity/issues) <br> [GitHub Project](https://github.com/Azure/aad-pod-identity/projects/3) | <ul><li>[Use with AKS](https://docs.microsoft.com/en-us/azure/aks/developer-best-practices-pod-security#use-pod-managed-identities)</li><li>[Use with AKS Engine](https://github.com/Azure/aks-engine/tree/master/examples/addons/aad-pod-identity)</li></ul> |
| [OPA Gatekeeper](https://github.com/open-policy-agent/gatekeeper) <br> ([releases](https://github.com/open-policy-agent/gatekeeper/releases)) | K8s native Open Policy Agent policy enforcement | CNCF: incubating <br> API: v1alpha1 and v1beta1 | [#kubernetes-policy](https://openpolicyagent.slack.com/archives/CDTN970AX) <br> [GitHub issues](https://github.com/open-policy-agent/gatekeeper/issues) | <ul><li>[Azure Policy for AKS](https://docs.microsoft.com/en-us/azure/governance/policy/concepts/rego-for-aks)</ul><li>[Azure Policy for AKS Engine](https://docs.microsoft.com/en-us/azure/governance/policy/concepts/aks-engine)</li><li>Azure Policy for Azure Arc connected clusters</li><ul> |
| [Keyvault Flexvol](https://github.com/Azure/kubernetes-keyvault-flexvol) <br> ([releases](https://github.com/Azure/kubernetes-keyvault-flexvol/releases)) | Mount Azure Keyvault secrets into pods | Azure: incubation <br> API: N/A | [GitHub issues](https://github.com/Azure/kubernetes-keyvault-flexvol/issues) | [Use with AKS](https://docs.microsoft.com/en-us/azure/aks/developer-best-practices-pod-security#use-azure-key-vault-with-flexvol) |
| [Secrets Store CSI Driver](http://sigs.k8s.io/secrets-store-csi-driver) <br> ([releases](https://github.com/kubernetes-sigs/secrets-store-csi-driver/releases)) <br> [Builds](https://testgrid.k8s.io/sig-auth-secrets-store-csi-driver#secrets-store-csi-driver-e2e-vault-postsubmit) | Integrates secrets stores with Kubernetes via a [Container Storage Interface (CSI)](https://kubernetes-csi.github.io/docs/) volume | CNCF: N/A <br> API: v1alpha1 | [#sig-auth](https://kubernetes.slack.com/archives/C0EN96KUY) <br> [GitHub issues](https://github.com/kubernetes-sigs/secrets-store-csi-driver/issues) |  |
| [Azure KeyVault Provider for Secrets Store CSI Driver](https://github.com/Azure/secrets-store-csi-driver-provider-azure) <br> ([releases](https://github.com/Azure/secrets-store-csi-driver-provider-azure/releases)) | Enables mounting AKV secrets as volumes in K8s pods | Azure: sandbox <br> API: N/A | [GitHub issues](https://github.com/Azure/secrets-store-csi-driver-provider-azure/issues) |  |


### Cloud Native Service Mesh

| Project & (artifacts) | Goal | Project State & <br> API Version | Communication | Use on Azure |
|---|---|---|---|---|
| [Service Mesh Interface (SMI) Spec](https://smi-spec.io/) | A standard interface for service meshes on Kubernetes | CNCF: sandbox ([pending](https://github.com/cncf/toc/pull/336)) <br> APIs: Traffic Split v1alpha3; Traffic Target v1alpha1; Traffic Spec v1alpha2; Traffic Metrics v1alpha1 | [#general](https://smi-spec.slack.com/archives/CJJF5M5NK) <br> [GitHub issues](https://github.com/deislabs/smi-spec/issues) |  |


### Container Runtime

| Project & (artifacts) | Goal | Project State & <br> API Version | Communication | Use on Azure |
|---|---|---|---|---|
| [Moby](https://github.com/moby/moby) <br> ([releases](https://github.com/moby/moby/releases)) | Toolkit for app containerization | Moby: ?? <br> API: N/A | [#opencontainers](https://opencontainers.slack.com/archives/C0LQVA03W) <br> [Moby Forums](https://forums.mobyproject.org/) <br> [GitHub issues](https://github.com/moby/moby/issues) | <ul><li>[Azure Kubernetes Service](https://docs.microsoft.com/en-us/azure/aks/)</li><li>[Azure Stack Hub](https://docs.microsoft.com/en-us/azure-stack/user/azure-stack-kubernetes-aks-engine-overview))</li><li>many more</li></ul> |
| [Containerd](https://github.com/containerd/containerd) <br> ([releases](https://github.com/containerd/containerd/releases)) | Complete container lifecycle management on Linux and Windows hosts | CNCF: graduated <br> API: N/A | [#opencontainers](https://opencontainers.slack.com/archives/C0LQVA03W) <br> [dev@opencontainers.org](https://groups.google.com/a/opencontainers.org/forum/#!forum/dev) <br> [GitHub issues](https://github.com/containerd/containerd/issues) | [Use with AKS Engine](https://github.com/Azure/aks-engine/blob/master/examples/kubernetes-containerd.json) |

## Project Maturity

Open source project maturity can be assessed on many dimensions including age, number of contributors, diversity of contributor employers, and many more. Two things you should consider are represented in the following bullets:

* Project state - The first entry in the Maturity column represents the project's status. Projects in the CNCF (kubernetes, kubernetes-sigs, prometheus, etc) use the [CNCF maturity model](https://github.com/cncf/toc/blob/master/process/graduation_criteria.adoc). Projects in the Azure, Microsoft, or deislabs GitHub orgs are working towards using the [guaduation guidelines](process/graduation_guidelines.md) defined in this repo. 
* [API or Feature Versions](https://kubernetes.io/docs/concepts/overview/kubernetes-api/#api-versioning) if relevant, are listed as the second entry of the Maturity column, and follow the Kubernetes convention except where noted

## Contributing

Want to get involved? The Azure Container Compute team welcomes contributions and suggestions. If you wonder what the Azure Container Compute team is working on, check out the [Project Board](https://github.com/Azure/container-compute-upstream/projects/1). If you would like to see the Azure Container Compute Upstream team work on something, first check if there is an [existing issue](https://github.com/Azure/container-compute-upstream/issues). If there isn't, please create a new one. If there is existing information elsewhere on the internet, please include the links.

This project is not setup for contributing code. It is intended only for tracking issues.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.
