# App Template Development Instructions

The `app-template` chart is a companion chart to the `common` library that provides a ready-to-use application deployment template.

## Structure

- `templates/common.yaml`: Initializes and loads the common library
- `values.schema.json`: JSON schema for validating values
- `values.yaml`: Default values for the chart

## Key Concepts

1. **Chart Dependencies**: The app-template depends on the common library chart
2. **Values Override**: The app-template provides sensible defaults while allowing for customization
3. **Release-specific Naming**: The chart automatically sets the nameOverride based on the release name

## Development Guidelines

### Making Changes to App Template

When modifying the app-template chart:

1. Ensure that changes align with the common library capabilities
2. Update the values schema if adding new parameters
3. Update the chart version in `Chart.yaml` following semver principles
4. Update the common library dependency version if needed

### Testing Changes

After making changes:

1. Run `task charts:lint` to validate chart syntax
2. Deploy a test application using the modified template
3. Verify that all resources are created correctly

### Updating Common Library Dependency

When updating the common library dependency:

1. Update the dependency version in `Chart.yaml`
2. Update the chart version appropriately
3. Document any breaking changes or new features in the release notes

### Best Practices for App Template

1. Keep the template as simple as possible
2. Document examples for different use cases
3. Provide sensible defaults that work for most applications
4. Use the values schema to provide guidance on valid configurations
