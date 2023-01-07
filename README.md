# Crossplane Basic to Advanced Demo

There are three demos in this repo to show different ways to use Crossplane to build a S3 bucket in AWS. The goal is to 
gain familiarity of how Crossplane works from using individual resources, to compositions and finally how Upbound builders
can make it easier and more standardized.

* Managed Resources - Build each resource on its own 
* Composite Resource Definition - Create a XRD and Composition to build everything with one API call
* IAM Builder - Same as #2, however this uses Upbound's IAM Builder functionality to automatically build the IAM and reduce configuration burden by 45%.

** The IAM Builder is only available for Upbound's existing or potential customers. 

## Setup
After cloning this repo, do the following.

### Install Provider
1. [Check the Upbound marketplace](https://marketplace.upbound.io/providers/upbound/provider-aws/) for the latest version of the provider (ie-v0.26.0).
2. Change the spec.package in[the provider config](./providers/aws-default-provider.yaml)
3. `kubectl -f providers/aws-default-provider.yaml`
4. `kubectl get providers` and verify INSTALLED and HEALTHY are true.

### Configure Provider
1. [Create a Kubernetes secret for AWS](https://docs.upbound.io/quickstart/provider-aws/#create-a-kubernetes-secret-for-aws)
2. Install the provider config `kubectl apply -f providers/aws-provider-cfg.yaml`
3. `kubectl get providerconfigs` and verify the default provider is created

## Demo

Go in to each folder below to follow the README for each section. These do not have to be done in order.
However, if you want to see the true power of Crossplane and Upbound's IAM Builder, follow them in order.

* [Managed Resources](./1-managed-resources)
* [Composite Resource Definition](./2-composite-resource-definition)
* [IAM Builder](./3-xrds-iam-builder)
