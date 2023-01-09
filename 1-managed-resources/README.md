# Managed Resources

This folder has each managed resource in a file to be built by itself as a single resource. Installing all of them will
create the following:

* One S3 bucket
* Ownership preferences on the S3 bucket
* A new role, policy and role policy attachment

This is a very basic approach to using Managed resources in Crossplane. It uses only the managed resources from the
provider and not within a composition.

## Steps
1. Follow [setup](../README.md)
2. In each file in the folder, search and replace the word **changeme** and replace with your own name.
3. Apply manifests in the folder:
   * `kubectl apply -f ./`
4. Verify managed resources: 
   * `kubectl get managed -l crossplane-demo=managed-resources`
5. Cleanup:
   * `kubectl delete -f ./`

## Next
* [Build the same resources in a composition](../2-composite-resource-definition)