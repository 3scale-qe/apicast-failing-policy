[![CircleCI](https://circleci.com/gh/3scale/apicast-example-policy.svg?style=svg)](https://circleci.com/gh/3scale/apicast-example-policy)

# APIcast Failing Policy

This policy is a simple policy that fails successfully during access phase or doesn't execute at all.

The configuration for the policy is as follow:

~~~JSON
{
   "name":"failing",
   "version":"0.1",
   "configuration":{
      "fail_access": True
   }
}
~~~

With the configuration above, the policy will fail during the access phase, it could be useful for testing purposes.

## OpenShift

To install this on OpenShift you can use provided template:

~~~shell
oc new-app -f openshift.yml --param AMP_RELEASE=2.2.0
~~~

The template creates new ImageStream for an Apicast image containing this policy.
Then it creates two BuildConfigs: one for building an image to apicast-policy ImageStream
and second one for creating new APIcast image copying just necessary code from that previous image.

# License

MIT
