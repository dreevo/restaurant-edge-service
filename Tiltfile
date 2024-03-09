# Build
custom_build(
     # Name of the container image
     ref = 'edge-service',
     tag = 'latest',
     # Command to build the container image
     command = '.\\gradlew.bat bootBuildImage --imageName edge-service:latest',
     # Files to watch that trigger a new build
     deps = ['build.gradle', 'src']
)
# Deploy
k8s_yaml(kustomize('k8s'))
# Manage
k8s_resource('edge-service', port_forwards=['9000'])