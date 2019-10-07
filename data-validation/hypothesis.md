# Hypothesis for Implementing Data Validation

The material in this document outlines a hypothesis for implementing a shape-based data validation mechanism in Solid to satisfy the stated [use cases](use-cases.md). This hypothesis will be validated and refined through critical review and prototyping, with the end result being input into a candidate proposal to the [Solid Specification](https://github.com/solid/specification).

# Draft considerations

* What is the lifecycle of posting/retrieving data when shapes are involved?
* Who applies validations and when are they able to do so?
* What are the rules for recursively applying data validation?
* How do we deal with exceptions? How are constraint violations reported back to the user?
* What are the ACL rules for accessing data validation resource content?
* What is the association between validation rules and a given resource?
* How do we deal with similar but different shapes? Is there any inferencing or reasoning?
* How are footprints related?
* Should regular expressions be used as part of defining shape constraints?
* Do we need to deal with shape transactions?
* How does one override an inheritable shape validation rule?
* Are validations kept in uniquely addressable LDP resources?
* How does one enable or disable an individual validator?
* If there are existing data/resources, what happens if enabling validation fails across all data?
* What if one enables validation across an entire (very large) pod? What are the performance/runtime implications?
* Does turning on validation require first validating (recursively) all of the resources under this validation resource?
* Can validation resources be remote? What if they change? Should they be "imported" into the POD system upon creation?
* If a validation resource has multiple SHACL/ShEx shapes, can those be configured to be "either" or "both"? I.e. the resource must match only one of the shapes, or alternatively, the resource must match both shapes.
* What happens if the validation shape is syntactically invalid? What if it remote vs. local?
