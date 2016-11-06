# CXF Proxy OSGI Example

### Introduction

Simple local proxy of remote endpoint

### Build

You will need to compile the example first:

	mvn install

Remarks:
- During the compilation phase, a unit test will be performed which simulates the
  client calling the web service exposed by our camel/cxf route.
- In Eclipse, I have used the following option when starting the junit test case. This option tells
  CXF that it must use log4j : -Dorg.apache.cxf.Logger=org.apache.cxf.common.logging.Log4jLogger

### Run

To run the example on Apache Karaf 2.4.x

#### Step 1: launch the server
	karaf / karaf.bat

#### Step 2: Add features required	
	features:install cxf
	features:install camel-spring
	features:install camel-jaxb
	features:install camel-cxf


#### Step 3: Deploy the example
	install -s mvn:ch.aymenfurter/camel-example-proxy/1.0.0-SNAPSHOT

#### Step 4: The GeoIP Proxy should be now exposed in your karaf runtime.	