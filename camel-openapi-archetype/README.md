# README #

This is a Maven archetype that generates a Camel/SpringBoot application with stubs for API endpoints generated from a provided OpenAPI document.
It is part of MS3's integration platform, [Tavros](https://github.com/MS3Inc/tavros).

### How do I get set up? ###

Clone the main branch of this repo. 

To build the archetype, `cd` into the archetype source and run `mvn clean install`.

If changes are made to the [OpenAPI plugin](https://github.com/MS3Inc/camel-restdsl-openapi-plugin), the version should be changed in `archetype-post-generate.groovy` by changing the `camelRestDslPluginVersion` variable.

### How do I run the archetype? ###

To run the archetype, `cd` to the directory where the new project will live and then run:

```bash
mvn archetype:generate \
-DarchetypeGroupId=com.ms3-inc.tavros \
-DarchetypeArtifactId=camel-openapi-archetype \
-DarchetypeVersion=<check-for-latest> \
-DgroupId=<groupId> \
-Dversion=0.1.0-SNAPSHOT \
-DartifactId=<project-name> \
-DspecificationUri=<path-of-your-spec>
````

Anything surrounded by an angle bracket in the above command should be replaced with the value you want. All the properties listed in the above command are required, and if any are removed/not provided, they will be prompted for. The exception to this is the `specificationUri` (OpenAPI file), where the default sample specification will be used if one isn't provided. To override this in interactive mode, when prompted for `Y`, enter something else such as `n`, and then re-provide the provided information and provide the specification when prompted.

The `-DpackageInPathFormat` and `-package` arguments should be supplied if your groupId has a dash in it, such as com.ms3-inc.  Leave them out if not needed. Here is an example of providing them:
```bash
-DpackageInPathFormat \
-Dpackage=com.ms3_inc.tavros \
-DgroupId=com.ms3-inc.tavros \
```

### Who do I talk to? ###

Contact:

* Mark Norton, mnorton@ms3-inc.com
* Jose Montoya, jmontoya@ms3-inc.com
* Rob Ratcliffe, rratcliffe@ms3-inc.com