# aws-codebuild-local-playground

## Resources

* [Announcing Local Build Support for AWS CodeBuild](https://aws.amazon.com/blogs/devops/announcing-local-build-support-for-aws-codebuild/)

## Running

```sh
# build CodeBuild image locally 
git clone https://github.com/aws/aws-codebuild-docker-images.git
cd aws-codebuild-docker-images/ubuntu/standard/2.0
docker build -t aws/codebuild/standard:2.0 .

# pull  CodeBuild local agent
docker pull amazon/aws-codebuild-local:latest --disable-content-trust=false

# cd to directory containing `buildspec.yml`
# NOTE: script was previously downloaded to `~/bin/codebuild_build.sh`
codebuild_build.sh -i 'aws/codebuild/standard:2.0' -a 'artifact-output' -c

```

