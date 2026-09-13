# cilium-policies-lab

A throwaway "policies repository" for demo 32 of [cilium-implementation-poc](https://github.com/ephico2real2/cilium-implementation-poc):
the place a reconciler (Argo CD, Flux, a pipeline) applies CiliumNetworkPolicies from. The workflow in
`.github/workflows/policy-pr.yml` is the PoC's E10 template, unchanged: given a Hubble flows file committed under
`flows/`, it runs `cf2cnp merge` (the 0.6.0 release binary, checksum verified) against the policy under `policies/`,
validates the result against Cilium 1.20.1's CRD offline, and opens a pull request. Nothing reaches a cluster from here.
