---

copyright:
  years: 2015, 2018
lastupdated: "2018-06-21"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}


# Tomcat
{: #tomcat_runtime}

Die Laufzeit von Tomcat in {{site.data.keyword.Bluemix}} basiert auf dem Buildpack 'java_buildpack'.
{: shortdesc}

Zum Verwenden der Tomcat-Laufzeit in {{site.data.keyword.Bluemix_notm}} müssen Sie das Buildpack 'java_buildpack' zusammen mit der Option '-b' angeben. Beispiel:

```
ibmcloud cf push &lt;myApp&gt; -p &lt;pathToMyApp&gt; -b java_buildpack
```

Weitere Informationen zur Tomcat-Laufzeit finden Sie in der [Readme-Datei zu 'java-buildpack'](https://github.com/cloudfoundry/java-buildpack/blob/master/README.md).

## Starteranwendung
{: #starter_application}

{{site.data.keyword.Bluemix_notm}} stellt eine Tomcat-Starteranwendung bereit. Die Tomcat-Starteranwendung ist eine einfache Tomcat-App, die Sie als Vorlage verwenden können. Sie können mit der Starter-App experimentieren, Änderungen an der {{site.data.keyword.Bluemix_notm}}-Umgebung vornehmen und diese mit einer Push-Operation übertragen. Hilfe zur Verwendung der Starteranwendung finden Sie in [Starteranwendungen verwenden](../common/starter_app_usage.html).

## Laufzeitversionen
{: #runtime_versions}

Sie können die Version von Tomcat, die von Ihrer App verwendet werden soll, mit der Umgebungsvariablen JBP_CONFIG_TOMCAT ändern.
Sie können die Version von Java, die von Ihrer App verwendet werden soll, mit der Umgebungsvariablen JBP_CONFIG_OPEN_JDK_JRE ändern.
Beide können in der Manifestdatei der Anwendung angegeben werden.  Beispiel:
```
    env:
        JBP_CONFIG_TOMCAT: '{tomcat: { version: 8.0.+ }}'
        JBP_CONFIG_OPEN_JDK_JRE: '{jre: { version: 1.8.0_+ }}'
```
{: codeblock}
Die aktuelle java_buildpack-Version ist v3.19, die die Tomcat-Standardversion 8.0.45 und die Java-Standardversion 1.8.0_141 enthält.
Weitere Informationen finden Sie in den Informationen zu Releases von [java-buildpack](https://github.com/cloudfoundry/java-buildpack/releases/tag/v3.13).

## HTTPS-Weiterleitung
{: #https_redirect}

Die Tomcat-Laufzeit kann so konfiguriert werden, dass sie internen {{site.data.keyword.Bluemix_notm}}-Proxys vertraut und die Weiterleitung von HTTP an HTTPS (SSL) zulässt.
Ändern Sie dazu die Datei 'server.xml', indem Sie für das Valve-Element 'RemoteIpValve' die Optionen 'internalProxies' und 'protocolHeader' festlegen.

Die Tomcat-Laufzeit [server.xml](https://github.com/cloudfoundry/java-buildpack/blob/master/resources/tomcat/conf/server.xml), die im Buildpack enthalten ist, legt standardmäßig nur das Element 'protocolHeader' des Valve-Elements 'RemoteIpValve' fest.  Um den HTTP-Datenverkehr an HTTPS in {{site.data.keyword.Bluemix_notm}} weiterzuleiten, konfigurieren Sie das Element 'RemoteIpValve' in Ihrer angepassten Datei 'server.xml' wie folgt:

```
 <Valve className='org.apache.catalina.valves.RemoteIpValve' protocolHeader='x-forwarded-proto' internalProxies='.*' />
```
{: codeblock}

Weitere Konfigurationsoptionen für RemoteIpValve finden Sie in der [Dokumentation zu Tomcat ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://tomcat.apache.org/tomcat-8.0-doc/api/org/apache/catalina/valves/RemoteIpValve.html).

# Zugehörige Links
{: #rellinks notoc}
## Allgemein
{: #general notoc}
* [java-buildpack](https://github.com/cloudfoundry/java-buildpack)
