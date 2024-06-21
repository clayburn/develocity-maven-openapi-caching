# Requirements

- Use OpenAPI Maven Plugin 7.6.0
- Explicitly declare an `output` property. By default, openapi will use `${project.build.directory}/generated-sources/openapi` or `${project.build.directory}/generated-test-sources/openapi`.
- Configure the  [build-helper-maven-plugin](https://www.mojohaus.org/build-helper-maven-plugin/usage.html) property to include the generated source directory.
- If using a [custom generator](https://github.com/OpenAPITools/openapi-generator/tree/master/modules/openapi-generator-maven-plugin#custom-generator), a [custom template engine](https://openapi-generator.tech/docs/templating/#custom-engines), or a [post-processor](https://openapi-generator.tech/docs/file-post-processing/), add the implementations as an [additional input](https://docs.gradle.com/develocity/maven-extension/current/#declaring_additional_inputs) to the goal.

# Unsupported

- Fine-grained tracking of `configOptions` and other Map objects
- Disabling caching when `configHelp` is enabled
- Handling `collapsedSpec` / `includeCollapsedSpecInArtifacts`, which have [a side effect](https://github.com/OpenAPITools/openapi-generator/blob/v7.6.0/modules/openapi-generator-maven-plugin/src/main/java/org/openapitools/codegen/plugin/CodeGenMojo.java#L585) of adding an artifact to the project
