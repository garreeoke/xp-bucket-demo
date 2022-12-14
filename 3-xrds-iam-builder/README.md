# Upbound Builder for IAM

This folder is very similar to the composite resource definition folder. However, the Upbound Builder is used to 
build all the IAM. It builds the following:

* One S3 bucket
* Ownership preferences on the S3 bucket
* A new role, policy and role policy attachment

This approach shows how using the Upbound Builder will automatically select and build the needed IAM (role, policy and policy attachment).
To see the differences, look at the compositions. The one using Upbound Builder decreases the configuration burden by 45%!

## Steps
1. Follow [setup](../README.md)
2. Install Upbound Builder for IAM (TBD - Upbound customers only)
3. Create the definition and composition on you cluster:
   * `kubectl apply -f defintion.yaml`
   * `kubectl apply -f composition.yaml`
4. Modify the claim file (examples/s3bucket-iambuilder.yaml) and modify **changme** to something else.
5. Apply the claim:
   * `kubectl apply -f examples/s3bucket-iambuilder.yaml`
6. Verify managed resources: 
   * `kubectl get managed -l crossplane.io/claim-name=crossplane-demo-changeme-iambuilder`
7. Cleanup:
   * `kubectl delete -f examples/s3bucket-iambuilder.yaml`
