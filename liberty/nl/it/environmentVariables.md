---

copyright:
  years: 2015, 2018
lastupdated: "2018-03-06"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}


# Variabili di ambiente
{: #environment_variables}

Variabili di ambiente supportate da Liberty for Java.

<table>
<tr>
<th align="left">Nome variabile di ambiente</th>
<th align="left">Descrizione</th>
</tr>

<tr>
<td>BLUEMIX_APP_MGMT_ENABLE</td>
<td>Abilita i [programmi di utilità di Gestione applicazioni](../common/app_mng.html)</td>
</tr>

<tr>
<td>BLUEMIX_APP_MGMT_INSTALL</td>
<td>Installa i [programmi di utilità di Gestione applicazioni](../common/app_mng.html)</td>
</tr>

<tr>
<td>IBM_LIBERTY_BETA</td>
<td>Abilita le [funzioni beta Liberty/](usingBetaFeatures.html)</td>
</tr>

<tr>
<td>JAVA_OPTS</td>
<td>Configura le [opzioni Java](customizingJRE.html)</td>
</tr>

<tr>
<td>JBP_CONFIG_DYNATRACEAPPMONAGENT</td>
<td>Configura le [informazioni di ubicazione dell'agent Dynatrace](dynatrace.html#configuring_liberty_app)</td>
</tr>

<tr>
<td>JBP_CONFIG_IBMJDK </td>
<td>Configura la [versione IBM JRE](customizingJRE.html)</td>
</tr>

<tr>
<td>JBP_CONFIG_LIBERTY</td>
<td>Configura varie opzioni di runtime Liberty incluse le [funzioni per i file WAR o EAR](optionsForPushing.html#stand_alone_apps)</td>
</tr>

<tr>
<td>JBP_CONFIG_OPENJDK</td>
<td>Configura la [versione di OpenJDK](customizingJRE.html)</td>
</tr>

<tr>
<td>JBP_CONFIG_SPRINGAUTORECONFIGURATION </td>
<td>Disabilita il [Spring Auto-Reconfiguration framework](https://github.com/cloudfoundry/java-buildpack/blob/master/docs/framework-spring_auto_reconfiguration.md). Per disabilitare, imposta il valore su enabled: false. </td>
</tr>

<tr>
<td>JBP_LOG_LEVEL</td>
<td>Imposta il livello di registrazione del pacchetto di build. Valori possibili: <b>DEBUG</b>, <b>INFO</b> (predefinito), <b>WARN</b>, <b>ERROR</b> o <b>FATAL</b></td>
</tr>

<tr>
<td>JVM</td>
<td>Selezione il [tipo JRE](customizingJRE.html)</td>
</tr>

<tr>
<td>JVM_ARGS</td>
<td>Imposta gli [argomenti JVM](customizingJRE.html)</td>
</tr>

<tr>
<td>LBP_SERVICE_CONFIG_xxxx</td>
<td>[Sovrascrivi congiurazione del servizio](autoConfig.html#override_service_config)</td>
</tr>

<tr>
<td>HTTP_PROXY</td>
<td>Imposta le informazioni del server proxy</td>
</tr>

<tr>
<td>HTTPS_PROXY</td>
<td>Imposta le informazioni del server proxy</td>
</tr>

<tr>
<td>services_autoconfig_excludes</td>
<td>Disabilita il servizio di [configurazione automatica.](autoConfig.html#opting_out)</td>
</tr>
</table>
{: caption="Tabella 1. Variabili di ambiente disponibili per Liberty for Java" caption-side="top"}

## Attributi disabilitati nel pacchetto di build Liberty for Java

Ci sono alcuni attributi che sono automaticamente disabilitati dal pacchetto di build Liberty e che non puoi sovrascrivere. Le variabili di ambiente e gli attributi di seguito indicati sono disabilitati.

### Tabella degli attributi disabilitati

<table>
<tr>
<th>Attributo disabilitato</th>
<th>Elemento</th>
</tr>

<tr>
<td>host</td>
<td>httpEndpoint</td>
</tr>

<tr>
<td>httpPort</td>
<td>httpEndpoint</td>
</tr>

<tr>
<td>trustHostHeaderPort</td>
<td>webContainer</td>
</tr>

<tr>
<td>andextractHostHeaderPort</td>
<td>webContainer</td>
</tr>

<tr>
<td>logDirectory</td>
<td>logging</td>
</tr>

<tr>
<td>consoleLogLevel</td>
<td>logging</td>
</tr>

<tr>
<td>enableWelcomePage</td>
<td>httpDispatcher</td>
</tr>
</table>
{: caption="Tabella 1. Attributi disabilitati da Liberty for Java" caption-side="top"}

# rellinks
{: #rellinks notoc}
## general
{: #general notoc}
* [Runtime Liberty](index.html)
* [Liberty Overview](https://www.ibm.com/support/knowledgecenter/SSEQTP_liberty/com.ibm.websphere.wlp.doc/ae/cwlp_about.html)
