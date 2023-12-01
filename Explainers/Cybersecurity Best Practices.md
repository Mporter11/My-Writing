# Best Cybersecurity Practices for Software Development

## Overview
Here you will find common security issues that may be found during security scans. This document includes brief descriptions and fixes for each issue.

**Please Note:** 
1. The code blocks shown are examples. Modify as needed and remember to always carefully balance security and feasibility.
2. Some of these issues may only apply to certain environments. Use data transforms where needed (e.g. Strict Transport Security (HSTS) Headers).

## Best Practice 1: Adding a Strict-Transport-Security Header
**Definition:** A protocol that encrypts communication and data transfer between the web browser and server to prevent malicious tampering.
* The Strict-Transport-Security Header (HSTS) forces an API request to upgrade to HTTPS if it is not already.
* Recommended to be applied to all requests at the server level setting by modifying the web.config file. Making this change at the transform file level will avoid any issues from happening to the localhost server. 
* The "max-age" should be set to a minimum of one year (31536000).

```
<configuration>
  <!-- Configuration settings for the web server -->
  <system.webServer>

    <!-- URL Rewrite settings -->
    <rewrite xdt:Transform="InsertIfMissing">
      <!-- Outbound rules for response rewriting -->
      <outboundRules xdt:Transform="InsertIfMissing">

        <!-- Rule for adding Strict-Transport-Security header when using HTTPS -->
        <rule name="Add Strict-Transport-Security when HTTPS" enabled="true" xdt:Transform="InsertIfMissing">
          <!-- Match the server variable for Strict-Transport-Security header -->
          <match serverVariable="RESPONSE_Strict_Transport_Security" pattern=".*" />

          <!-- Conditions for applying the rule -->
          <conditions>
            <!-- Apply the rule only if the request is made over HTTPS -->
            <add input="{HTTPS}" pattern="on" ignoreCase="true" />
          </conditions>

          <!-- Rewrite action to add the Strict-Transport-Security header -->
          <action type="Rewrite" value="max-age=31536000; includeSubDomains; preload" />
        </rule>

      </outboundRules>
    </rewrite>

    <!-- Static content settings -->
    <staticContent xdt:Transform="InsertIfMissing">
      
      <!-- Client cache settings -->
      <clientCache cacheControlMode="UseMaxAge" xdt:Transform="InsertIfMissing" />

      <!-- Remove all existing client cache settings -->
      <clientCache cacheControlMode="UseMaxAge" xdt:Transform="RemoveAll" />

      <!-- Add custom client cache settings -->
      <clientCache cacheControlMode="UseMaxAge" cacheControlMaxAge="7.01:00:00" cacheControlCustom="public" xdt:Transform="Insert" />
      
    </staticContent>

  </system.webServer>
</configuration>

```

## Best Practice 2: Setting a Content Security Policy Header 
**Definition:** A Content Security Policy Header (CSP) enables a browser to define a set of rules regarding the types of content a web page is allowed to load or execute.
* CSPs vary greatly from site to site and within a site itself. If a site has different sections with different needs, use different CSPs with the <location> tag.
* Changes to CSP can easily break a website. Test all changes on multiple pages in different scenarios (CRO processes, tag manager tags, etc.).

```
<!-- Site wide CSP.  /configuration/system.webServer/httpProtocol -->
<httpProtocol>
    <customHeaders>
        <remove name="Content-Security-Policy" />
        <add name="Content-Security-Policy" value="default-src https:" />
    </customHeaders>
</httpProtocol>
 
<!-- Path specific CSP. /configuration/location  -->
<!-- This is Umbraco specific. Depending on plugins, it may be mirrored to '<location path="App_Plugins">' or other path (execution path) invoked context. -->
<location path="umbraco">
    <system.webServer>
        <urlCompression doStaticCompression="false" doDynamicCompression="false" dynamicCompressionBeforeCache="false" />
        <httpProtocol>
            <customHeaders>
                <remove name="Content-Security-Policy" />
                <add name="Content-Security-Policy" value="default-src 'self';script-src 'self' 'unsafe-inline' 'unsafe-eval';style-src https: data: * 'unsafe-inline';img-src https: data: 'unsafe-inline'" />
            </customHeaders>
        </httpProtocol>
    </system.webServer>
</location>
```

## Best Practice 3: Avoiding Padding Oracle Attacks
**Definition:** A "padded" data block sets a specific length requirement to ensure protection from an attack.
* Hackers will search for vulnerabilities by sending ciphertext to the padded system and observing the returned error message or page. 
* If the returned error message is different for an encrypted error and a generic error, it's possible for an attacker to determine what is a valid encrypted string and what isn't, making it easier to reverse the private key on the server.
* The strongest defense against an attack is to define the specific error redirects and messages that should return.
* Code since 2012 already has a protected baseline <system.web configuration> tag.

```
<configuration>
    <!-- Root element for the configuration settings of the application -->

    <system.web>
        <!-- Configuration settings specific to the web application -->

        <customErrors defaultRedirect="~/Error.aspx" mode="RemoteOnly" redirectMode="ResponseRewrite">
            <!-- Custom error handling configuration -->

            <error statusCode="404" redirect="/404" />
            <!-- Specific error configuration: Redirect to "/404" when the HTTP status code is 404 (Not Found) -->
        </customErrors>

    </system.web>
</configuration>
```
