Absolutely! Here is the README.md again, with the project structure included inside fenced Markdown code blocks, so you can copy-paste it cleanly:

⸻


# Spring SOAP Web Service Example

This project is a **Spring Boot SOAP Web Service** implemented by following the official [Spring.io guide](https://spring.io/guides/gs/producing-web-service).  
I completed this tutorial independently to learn about SOAP web services, WSDL exposure, and JAXB schema-based contract generation.

---

## 📚 Overview

This application:

✅ Exposes a SOAP endpoint to fetch country details (name, population, capital, currency).  
✅ Generates Java classes from an XSD schema (`countries.xsd`) using JAXB.  
✅ Publishes a WSDL for client consumption.

---

## 🛠 Technologies Used

- Java 21
- Spring Boot 3.x
- Spring Web Services
- JAXB
- Maven
- SOAP UI / cURL for testing

---

## 🧩 Project Structure

```plaintext
src/
  main/
    java/
      com.soap.tutorial.app.producingwebservice/
        CountryEndpoint.java                  # Handles incoming SOAP requests
        CountryRepository.java                # Contains country data
        WebServiceConfig.java                 # Configures SOAP servlet and WSDL
        ProducingWebServiceApplication.java   # Main app entry point
    resources/
      countries.xsd                           # XML Schema Definition
      application.properties


⸻

🌐 Running the Application

1️⃣ Build and run the service:

mvn clean spring-boot:run

The service will start on:

http://localhost:8080


⸻

📝 WSDL Location

Once running, the WSDL is available at:

http://localhost:8080/ws/countries.wsdl

This WSDL describes the SOAP operations and schema for clients.

⸻

🚀 Testing the Service

Using cURL

Create a request.xml file with the following content:

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/"
                  xmlns:gs="http://spring.io/guides/gs-producing-web-service">
   <soapenv:Header/>
   <soapenv:Body>
      <gs:getCountryRequest>
         <gs:name>Spain</gs:name>
      </gs:getCountryRequest>
   </soapenv:Body>
</soapenv:Envelope>

Run this command to send the request:

curl --header "Content-Type: text/xml" --data @request.xml http://localhost:8080/ws

You will receive a SOAP response containing the country details.

⸻

Using SOAP UI
	1.	Create a new SOAP Project.
	2.	Enter the WSDL URL:

http://localhost:8080/ws/countries.wsdl


	3.	Create a request for the getCountry operation.
	4.	Fill the request body with the sample XML above.
	5.	Click Submit to get the response.

⸻

🎯 What I Learned
	•	How to expose SOAP endpoints in Spring Boot.
	•	Generating Java classes from an XSD schema with JAXB.
	•	Configuring a DefaultWsdl11Definition for WSDL exposure.
	•	Testing SOAP services using cURL and SOAP UI.
	•	Understanding SOAP message structure.

⸻

📄 Reference

This project is based on the official Spring guide:
Producing a SOAP Web Service

⸻


---

✅ **Usage:**
- Save this as `README.md` in your project root.
- This includes *everything*, including a properly formatted project structure block.

If you want help refining further, just let me know!
