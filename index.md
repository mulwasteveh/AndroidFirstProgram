### An introductory knowledge on Web Services Description Language
Web services Description Language is the standard organization for depicting a web service. WSDL was grown mutually by IBM and Microsoft. it is an XML-based convention for data trade in decentralized and disseminated conditions or environments which are distributed. WSDL is regularly utilized in mix with SOAP and RESTful webservices to give web administrations or services over the Internet. A customer program interfacing with a web service can peruse the WSDL to figure out which capacities are accessible on the server. Any extraordinary datatypes utilized are implanted in the WSDL record as XML Schema. The customer would then be able to utilize RESTful web services to really call one of the capacities recorded in the WSDL. Below is a demo that gives a demonstration of a Web Service Description language program. Once you import WSDL, the WSDL is authenticated in contradiction of the WS-I Basic Profile. So as a programmer you must put in place validation errors before the message, library or application set can be positioned. These validations warnings indicate potential interoperability problems but do not prevent deployment problems. However, the validated WSDL becomes an integral part of the message, library as well as the application.
```xml
<?xml version="1.0" encoding="UTF-8"?>
<description xmlns="http://www.w3.org/ns/wsdl"
    xmlns:tns="http://www.tmsws.com/wsdl20sample"
    xmlns:whttp="http://schemas.xmlRESTful.org/wsdl/http/"
    xmlns:wRESTful="http://schemas.xmlRESTful.org/wsdl/RESTful/"
    targetNamespace="http://www.tmsws.com/wsdl20sample">

    <documentation>
        This is a sample Web Service Description Language 2.0 document.
    </documentation>

    <!-- Abstract type -->
    <types>
        <xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema"
            xmlns="http://www.tmsws.com/wsdl20sample"
            targetNamespace="http://www.example.com/wsdl20sample">

            <xs:element name="Request"> ... </xs:element>
            <xs:element name="Response"> ... </xs:element>
        </xs:schema>
    </types>

    <!-- These are Abstract interfaces -->
    <interface name="First_Interface">
        <fault name="First_Error" element="tns:response"/>
        <operation name="Get" pattern="http://www.w3.org/ns/wsdl/in-out">
            <input messageLabel="In" element="tns:Request"/>
            <output messageLabel="Out" element="tns:Response"/>
        </operation>
    </interface>

    <!-- Concrete Binding Over HTTP -->
    <binding name="HttpBinding" interface="tns:First_Interface"
        type="http://www.w3.org/ns/wsdl/http">
        <operation ref="tns:Get" whttp:method="GET"/>
    </binding>

    <!-- RESTful web service Endpoint interface-->
    <service name="First_Service" interface="tns:First_Interface">
        <endpoint name="HttpEndpoint"
            binding="tns:HttpBinding"
            address="http://www.example.com/rest/"/>
        <endpoint name="RESTfulEndpoint"
            binding="tns:RESTfulBinding"
            address="http://www.example.com/RESTful/"/>
    </service>
</description>
```

### RESTful web service Endpoint interface
REST is gotten from RESTful; it stands for REpresentational State Transfer. A RESTful web service Endpoint interface in that interface in the RESTful web services that entails a set of operations and each of the operations portraying a simplified interaction between the RESTful web services and the clients involved. Actually, these Endpoint interfaces uses the Web Service Description Language files to enhance or enable sharing of descriptions with the clients involved. The RESTful Endpoint interfaces has a displayed property name referred to as a base URL which acts as the Uniform resource Locator for all REST communications adjoined by the REST service Endpoint interface we are talking about. For instance, there might be a group of some resources linked or related with a certain library where we can find authors, borrowers and even books. Each of the listed resources above represents a certain resources type regarding on which queries and actions can be performed. Now, all of these can be accessed through the REST Uniform Resource Locators.  Java API for XML Web Services (JAX-WS) documentation provides additional guides on how to deploy RESTful webservices. Below is a way in which we offer RESTful web services Endpoint interface in java. Below is a sample of how you can make a RESTful web service Endpoint interface;
```java
<!-- RESTful web service Endpoint interface-->
    <service name="First_Service" interface="tns:First_Interface">
        <endpoint name="HttpEndpoint"
            binding="tns:HttpBinding"
            address="http://www.example.com/rest/"/>
        <endpoint name="RESTfulEndpoint"
            binding="tns:RESTfulBinding"
            address="http://www.example.com/RESTful/"/>
    </service>
```
### Web Service Execution
This is an action which offers an automated way of calling a web service method using the Uniform Resource Locator (URL) or even using the WSDL document. The web service execution supports static values, strings and numbers which are standard parameters, support for structure and static values. In simple terms, the web service execution action queries various methods and their related parameters, also allows either one method or a set of various methods to be called and the essential parameters to be issued out for an essential method call and be positioned in a respective web service. Moreover, this action may need the use of one structure as parameter as well as the use of more structures as parameters. While performing the execution, if any structures are needed, you must initially use “Define Type” as well as “Create Object” to create these structures as parameters and encompass them onto the fundamental action during the design time. These structures are stored in specific memories during the web service execution. Once the method call is executed, all the memory structures are automatically deleted from where they are stored. Some automate variable is specified at the design time which now upon the completion of these method calls the returned data is stored. Below is a declaration of web service execution using markup language;
```xml
<AMEXECUTEWEBSERVICE WSDLURL="asa" TYPENAME="text" METHODNAME="text" RESULTVARIABLE="text" RESULTSTRUCTURE="text" PROTOCOL="text (options)" AUTHENTICATIONTYPE="text (options)" USERNAME="text" PASSWORD="text" CERTIFICATE="text" PASSPHRASE="text"><Argument ArgType="text" ArgValue="text" /></AMEXECUTEWEBSERVICE>
```
### RESTful API
A RESTful API is a compositional style for an Application Program Interface (API) that utilizes HTTP protocols to access and utilize information. Such kind of information can be utilized to various information types such as PUT, GET, DELETE or even the POST types. These information types allude to the perusing, making and refreshing of tasks regarding to assets. However, we can define RESTful API as the RESTful web services which is an architectural style to communications commonly or mostly used in development of web services.
A RESTful API separates a transaction to make a progression of little modules. Every module tends to a basic piece of the exchange. This particularity gives engineers a great deal of adaptability, yet it very well may be moving for engineers to plan their REST API without any preparation. As of now, a few organizations give models to designers to utilize; the models given by Amazon S3, Cloud Data Management Interface (CDMI) and OpenStack Swift are the most famous.
