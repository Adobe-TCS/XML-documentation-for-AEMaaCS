> [!NOTE]  
> Starting AEM Guides release 2024.2.0, this process has now been deprecated. For the correct process to install AEM Guides on AEM Cloud Service please refer this [link](https://experienceleague.adobe.com/docs/experience-manager-guides/using/release-info/release-notes/cloud-release-notes/deploy-xml-on-aemaacs.html?lang=en)

# **Adobe Experience Manager Guides**

## Overview:

**Adobe Experience Manager Guides** (previously XML Documentation for Adobe Experience Manager) adds native DITA support to AEM. With this integration, it provides an end-to-end, enterprise-class, component content management system (CCMS) for DITA-based content creation and delivery. It provides all the core capabilities of a CCMS like version management, web-based collaboration, review &amp; approval, translation, search and reporting. It also provides a single-click publishing capability for DITA content to a mobile responsive web format, in addition to popular formats like PDF, EPUB, etc.

**NOTE:** This repo is only for new AEM cloud users. It contains the complete maven archetype AEM project with integrated Guides solution to get started.You should just replace the code generated by the cloud manager with this code to avoid any manual integration of Guides solution

Existing AEM cloud users need to use the below **Guides Installer for AEMaaCS** repository to integrate the Guides solution in their code.

[https://github.com/Adobe-TCS/DoX-Installer-for-AEMaaCS](https://github.com/Adobe-TCS/DoX-Installer-for-AEMaaCS)

## Prerequisites

Install the following tools.

- Install [Git Client](https://git-scm.com/) (Preferably Git-CLI)
- Install [Java](https://www.oracle.com/in/java/technologies/javase-downloads.html)
- Set [JAVA\_HOME](https://www.appsdeveloperblog.com/how-to-set-java_home-on-mac/)
- Install [Maven](https://maven.apache.org/download.cgi) ([Maven Tutorial](https://maven.apache.org/guides/getting-started/maven-in-five-minutes.html))
- Copy this [Settings.xml](https://git.corp.adobe.com/AdobeStarling/starling/blob/develop/settings.xml) to the .m2 folder in your user directory.
- Install [NodeJS](https://nodejs.org/en/download/) ([NodeJS Tutorial](https://www.codeschool.com/courses/real-time-web-with-node-js))
- Install a Java IDE (Eclipse with Maven plugin / Netbeans etc..)
- Setup an AEM instance ([Codex](https://codex.corp.adobe.com/))
- Install [Python 3.x](https://www.python.org/downloads/) (Optional)
- Install Sublime Text with AEM Plugin or Brackets with AEM plugin (Optional)
- Install any WebDAV client ([CarotDAV](http://rei.to/carotdav_en.html)) (Optional)

## How to Build

- Create a clone of this Git repository.

  git clone [https://github.com/Adobe-TCS/XML-documentation-for-AEMaaCS.git](https://github.com/Adobe-TCS/XML-documentation-for-AEMaaCS.git)

- Replace the Cloud Manager default code with this repository code.
- Deploy the code in cloud manager. For more details on deploying code, see [Deploying Code with Cloud Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-manager/using/how-to-use/deploying-code.html) in AEM&#39;s documentation.

## Modules

The main parts of the template are:

- core: Java bundle containing all core functionality like OSGi services, listeners or schedulers, as well as component-related Java code such as servlets or request filters.
- dox: Guides installer for cloud service.
    - dox.config.override : contains samples for upgrading Guides solution osgi properties
    - dox.installer: contains code to install Guides solution. Add the credentails shared in welcome email in this module's pom
    - dox.openinoxygen.installer: contains code to install open-in-oxygen button. Add the credentails shared in welcome email in this module's pom
- it.tests: Java based integration tests
- ui.apps: contains the /apps (and /etc) parts of the project, ie JS&amp;CSS clientlibs, components, and templates
- ui.content: contains sample content using the components from the ui.apps
- ui.config: contains runmode specific OSGi configs for the project
- ui.frontend: an optional dedicated front-end build mechanism (Angular, React or general Webpack project)
- ui.tests: Selenium based UI tests
- all: a single content package that embeds all of the compiled modules (bundles and content packages) including any vendor dependencies
- analyse: this module runs analysis on the project which provides additional validation for deploying into AEMaaCS

## Maven settings

The project comes with the auto-public repository configured. To setup the repository in your Maven settings, refer to:

[http://helpx.adobe.com/experience-manager/kb/SetUpTheAdobeMavenRepository.html](http://helpx.adobe.com/experience-manager/kb/SetUpTheAdobeMavenRepository.html)
