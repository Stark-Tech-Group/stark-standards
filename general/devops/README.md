| Code     | Description                                                                                                                          |
|----------|--------------------------------------------------------------------------------------------------------------------------------------|
| devop-1  | All projects are required to have a Continuous Integration pipeline                                                                  |
| devop-2  | All projects are required to have a Continuous Deployment pipeline                                                                   |
| devop-3  | CI should execute test, run lint checks, build production and test images, build artifacts(.jar, .war, exe), and run security checks |
| devop-4  | CD should deploy artifacts and images to registries(maven/gradle, docker) and production or staging environments                     |
| devop-5  | CI pipeline should be designed as logical steps( pull->lint->unit-test->integration test->build/compile                              |
| devop-6  | All generated documents, reports, and artifacts will be stored with the pipeline execution                                           |
| devop-7  | CI will be triggered on push and on PR                                                                                               |
| devop-8  | CD will be triggered after PR into base/production branch                                                                            |
