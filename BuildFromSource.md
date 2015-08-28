# Instructions #

Steps to Compile from Source:
  1. download & configure the Android source tree
  1. download postgresql-8.4.1
  1. download the psqldroid patch
  1. extract the postgres archive and move the directory to external/postgresql under your Android source tree
  1. change into the external/postgresql directory
  1. apply the psqldroid patch
  1. run 'sh create-symbolic-links.sh'
  1. change to the root of the android source tree
  1. make psql

Notes:
  * This is known to work with the Android Donut release, but probably others as well
  * Once the compilation completes, you will find binaries under target/out/...