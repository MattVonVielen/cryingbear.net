+++
title = "Maven: I still just don't get it."
slug = "2011-01-11-maven-i-still-just-dont-get-it"
published = 2011-01-11T22:08:00.004000-06:00
author = "Matt Campbell"
tags = []
+++
I'm in the process of trying to kick off another hobby coding project,
this time in the Android ecosystem (toxic as that seems to be - more on
that in another post someday)[^1]. Remembering how a few current and former
colleagues have raved about Maven, especially how one particular former
colleague told me I needed to "suck it up and learn Maven", I decided to
give it another shot.  
  
Grabbing a very small and straightforward sample pom.xml from a how-to
online, I modified it slightly to correct the project name, and decided
to see what would happen if I ran it with no source - just the pom.xml
in an empty directory. I ran `mvn clean` and wasn't totally surprised
that it took **FOUR MINUTES** to do, essentially, nothing. The insane
amount of output is below.[^2] &lt;hyperbole&gt;I suppose the good news is
that now I've reached the end of the internet and have access to all
software, everywhere...&lt;/hyperbole&gt;  
  
```text
xenolinguist@XenoMac$ mvn clean

[INFO] Scanning for projects...
Downloading: http://repo1.maven.org/maven2/com/jayway/maven/plugins/android/generation2/maven-android-plugin/2.8.3/maven-android-plugin-2.8.3.pom 
Downloading: http://repo1.maven.org/maven2/com/jayway/maven/plugins/android/generation2/maven-android-plugin/2.8.3/maven-android-plugin-2.8.3.jar 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven-artifact/2.2.1/maven-artifact-2.2.1.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven/2.2.1/maven-2.2.1.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven-parent/11/maven-parent-11.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/apache/5/apache-5.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-utils/1.5.15/plexus-utils-1.5.15.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus/2.0.2/plexus-2.0.2.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven-model/2.2.1/maven-model-2.2.1.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven-plugin-api/2.2.1/maven-plugin-api-2.2.1.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven-project/2.2.1/maven-project-2.2.1.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven-settings/2.2.1/maven-settings-2.2.1.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-interpolation/1.11/plexus-interpolation-1.11.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-components/1.1.14/plexus-components-1.1.14.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-container-default/1.0-alpha-9-stable-1/plexus-container-default-1.0-alpha-9-stable-1.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-containers/1.0.3/plexus-containers-1.0.3.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus/1.0.4/plexus-1.0.4.pom 
Downloading: http://repo1.maven.org/maven2/junit/junit/3.8.1/junit-3.8.1.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-utils/1.0.4/plexus-utils-1.0.4.pom 
Downloading: http://repo1.maven.org/maven2/classworlds/classworlds/1.1-alpha-2/classworlds-1.1-alpha-2.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven-profile/2.2.1/maven-profile-2.2.1.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven-artifact-manager/2.2.1/maven-artifact-manager-2.2.1.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven-repository-metadata/2.2.1/maven-repository-metadata-2.2.1.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/wagon/wagon-provider-api/1.0-beta-6/wagon-provider-api-1.0-beta-6.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/wagon/wagon/1.0-beta-6/wagon-1.0-beta-6.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-utils/1.4.2/plexus-utils-1.4.2.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus/1.0.11/plexus-1.0.11.pom 
Downloading: http://repo1.maven.org/maven2/backport-util-concurrent/backport-util-concurrent/3.1/backport-util-concurrent-3.1.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven-plugin-registry/2.2.1/maven-plugin-registry-2.2.1.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven-core/2.2.1/maven-core-2.2.1.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/wagon/wagon-file/1.0-beta-6/wagon-file-1.0-beta-6.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/wagon/wagon-providers/1.0-beta-6/wagon-providers-1.0-beta-6.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven-plugin-parameter-documenter/2.2.1/maven-plugin-parameter-documenter-2.2.1.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/wagon/wagon-http-lightweight/1.0-beta-6/wagon-http-lightweight-1.0-beta-6.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/wagon/wagon-http-shared/1.0-beta-6/wagon-http-shared-1.0-beta-6.pom 
Downloading: http://repo1.maven.org/maven2/nekohtml/xercesMinimal/1.9.6.2/xercesMinimal-1.9.6.2.pom 
Downloading: http://repo1.maven.org/maven2/nekohtml/nekohtml/1.9.6.2/nekohtml-1.9.6.2.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/wagon/wagon-http/1.0-beta-6/wagon-http-1.0-beta-6.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/wagon/wagon-webdav-jackrabbit/1.0-beta-6/wagon-webdav-jackrabbit-1.0-beta-6.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/jackrabbit/jackrabbit-webdav/1.5.0/jackrabbit-webdav-1.5.0.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/jackrabbit/jackrabbit-parent/1.5.0/jackrabbit-parent-1.5.0.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/apache/4/apache-4.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/jackrabbit/jackrabbit-jcr-commons/1.5.0/jackrabbit-jcr-commons-1.5.0.pom 
Downloading: http://repo1.maven.org/maven2/org/slf4j/slf4j-api/1.5.3/slf4j-api-1.5.3.pom 
Downloading: http://repo1.maven.org/maven2/org/slf4j/slf4j-parent/1.5.3/slf4j-parent-1.5.3.pom 
Downloading: http://repo1.maven.org/maven2/commons-httpclient/commons-httpclient/3.0/commons-httpclient-3.0.pom 
Downloading: http://repo1.maven.org/maven2/commons-codec/commons-codec/1.2/commons-codec-1.2.pom 
Downloading: http://repo1.maven.org/maven2/org/slf4j/slf4j-nop/1.5.3/slf4j-nop-1.5.3.pom 
Downloading: http://repo1.maven.org/maven2/org/slf4j/slf4j-jdk14/1.5.6/slf4j-jdk14-1.5.6.pom 
Downloading: http://repo1.maven.org/maven2/org/slf4j/slf4j-parent/1.5.6/slf4j-parent-1.5.6.pom 
Downloading: http://repo1.maven.org/maven2/org/slf4j/slf4j-api/1.5.6/slf4j-api-1.5.6.pom 
Downloading: http://repo1.maven.org/maven2/org/slf4j/jcl-over-slf4j/1.5.6/jcl-over-slf4j-1.5.6.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/reporting/maven-reporting-api/2.2.1/maven-reporting-api-2.2.1.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/reporting/maven-reporting/2.2.1/maven-reporting-2.2.1.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/doxia/doxia-sink-api/1.1/doxia-sink-api-1.1.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/doxia/doxia/1.1/doxia-1.1.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/doxia/doxia-logging-api/1.1/doxia-logging-api-1.1.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-container-default/1.0-alpha-30/plexus-container-default-1.0-alpha-30.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-containers/1.0-alpha-30/plexus-containers-1.0-alpha-30.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven-error-diagnostics/2.2.1/maven-error-diagnostics-2.2.1.pom 
Downloading: http://repo1.maven.org/maven2/commons-cli/commons-cli/1.2/commons-cli-1.2.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/commons/commons-parent/11/commons-parent-11.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/wagon/wagon-ssh-external/1.0-beta-6/wagon-ssh-external-1.0-beta-6.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/wagon/wagon-ssh-common/1.0-beta-6/wagon-ssh-common-1.0-beta-6.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-interactivity-api/1.0-alpha-6/plexus-interactivity-api-1.0-alpha-6.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-interactivity/1.0-alpha-6/plexus-interactivity-1.0-alpha-6.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-components/1.1.9/plexus-components-1.1.9.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus/1.0.10/plexus-1.0.10.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-utils/1.4/plexus-utils-1.4.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus/1.0.9/plexus-1.0.9.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven-plugin-descriptor/2.2.1/maven-plugin-descriptor-2.2.1.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-interactivity-api/1.0-alpha-4/plexus-interactivity-api-1.0-alpha-4.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven-monitor/2.2.1/maven-monitor-2.2.1.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/wagon/wagon-ssh/1.0-beta-6/wagon-ssh-1.0-beta-6.pom 
Downloading: http://repo1.maven.org/maven2/com/jcraft/jsch/0.1.38/jsch-0.1.38.pom 
Downloading: http://repo1.maven.org/maven2/classworlds/classworlds/1.1/classworlds-1.1.pom 
Downloading: http://repo1.maven.org/maven2/org/sonatype/plexus/plexus-sec-dispatcher/1.3/plexus-sec-dispatcher-1.3.pom 
Downloading: http://repo1.maven.org/maven2/org/sonatype/spice/spice-parent/12/spice-parent-12.pom 
Downloading: http://repo1.maven.org/maven2/org/sonatype/forge/forge-parent/4/forge-parent-4.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-utils/1.5.5/plexus-utils-1.5.5.pom 
Downloading: http://repo1.maven.org/maven2/org/sonatype/plexus/plexus-cipher/1.4/plexus-cipher-1.4.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/plugins/maven-dependency-plugin/2.1/maven-dependency-plugin-2.1.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/plugins/maven-plugins/12/maven-plugins-12.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven-parent/9/maven-parent-9.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven-artifact/2.0.9/maven-artifact-2.0.9.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven/2.0.9/maven-2.0.9.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven-parent/8/maven-parent-8.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven-plugin-api/2.0.9/maven-plugin-api-2.0.9.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven-project/2.0.9/maven-project-2.0.9.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven-model/2.0.9/maven-model-2.0.9.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven-core/2.0.9/maven-core-2.0.9.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-archiver/1.0-alpha-9/plexus-archiver-1.0-alpha-9.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-utils/1.4.1/plexus-utils-1.4.1.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-io/1.0-alpha-1/plexus-io-1.0-alpha-1.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-utils/1.4.6/plexus-utils-1.4.6.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/shared/file-management/1.1/file-management-1.1.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/shared/maven-shared-components/4/maven-shared-components-4.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven-parent/4/maven-parent-4.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/apache/3/apache-3.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven-plugin-api/2.0/maven-plugin-api-2.0.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven/2.0/maven-2.0.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/shared/maven-shared-io/1.0/maven-shared-io-1.0.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven-artifact/2.0.2/maven-artifact-2.0.2.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven/2.0.2/maven-2.0.2.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven-artifact-manager/2.0.2/maven-artifact-manager-2.0.2.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/wagon/wagon-provider-api/1.0-alpha-6/wagon-provider-api-1.0-alpha-6.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/wagon/wagon/1.0-alpha-6/wagon-1.0-alpha-6.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-utils/1.2/plexus-utils-1.2.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus/1.0.5/plexus-1.0.5.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-container-default/1.0-alpha-9/plexus-container-default-1.0-alpha-9.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/shared/maven-dependency-analyzer/1.1/maven-dependency-analyzer-1.1.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/shared/maven-shared-components/10/maven-shared-components-10.pom 
Downloading: http://repo1.maven.org/maven2/asm/asm/3.0/asm-3.0.pom 
Downloading: http://repo1.maven.org/maven2/asm/asm-parent/3.0/asm-parent-3.0.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-utils/1.5.1/plexus-utils-1.5.1.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven-project/2.0.5/maven-project-2.0.5.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven/2.0.5/maven-2.0.5.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven-parent/5/maven-parent-5.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven-model/2.0.5/maven-model-2.0.5.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven-artifact/2.0.5/maven-artifact-2.0.5.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/shared/maven-dependency-tree/1.2/maven-dependency-tree-1.2.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/shared/maven-shared-components/9/maven-shared-components-9.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven-project/2.0.8/maven-project-2.0.8.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven/2.0.8/maven-2.0.8.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven-parent/6/maven-parent-6.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/shared/maven-common-artifact-filters/1.0/maven-common-artifact-filters-1.0.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/shared/maven-shared-components/8/maven-shared-components-8.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven-parent/7/maven-parent-7.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven-artifact/2.0.8/maven-artifact-2.0.8.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/shared/maven-plugin-testing-harness/1.1/maven-plugin-testing-harness-1.1.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/shared/maven-shared-components/7/maven-shared-components-7.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven-project/2.0/maven-project-2.0.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven-core/2.0/maven-core-2.0.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-archiver/1.0-alpha-7/plexus-archiver-1.0-alpha-7.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-components/1.1.6/plexus-components-1.1.6.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus/1.0.8/plexus-1.0.8.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/reporting/maven-reporting-api/2.0.6/maven-reporting-api-2.0.6.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/reporting/maven-reporting/2.0.6/maven-reporting-2.0.6.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven/2.0.6/maven-2.0.6.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/reporting/maven-reporting-impl/2.0.4/maven-reporting-impl-2.0.4.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/reporting/maven-reporting/2.0.4/maven-reporting-2.0.4.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven/2.0.4/maven-2.0.4.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven-project/2.0.4/maven-project-2.0.4.pom 
Downloading: http://repo1.maven.org/maven2/commons-validator/commons-validator/1.2.0/commons-validator-1.2.0.pom 
Downloading: http://repo1.maven.org/maven2/commons-beanutils/commons-beanutils/1.7.0/commons-beanutils-1.7.0.pom 
Downloading: http://repo1.maven.org/maven2/commons-logging/commons-logging/1.0.3/commons-logging-1.0.3.pom 
Downloading: http://repo1.maven.org/maven2/commons-digester/commons-digester/1.6/commons-digester-1.6.pom 
Downloading: http://repo1.maven.org/maven2/commons-beanutils/commons-beanutils/1.6/commons-beanutils-1.6.pom 
Downloading: http://repo1.maven.org/maven2/commons-logging/commons-logging/1.0/commons-logging-1.0.pom 
Downloading: http://repo1.maven.org/maven2/commons-collections/commons-collections/2.1/commons-collections-2.1.pom 
Downloading: http://repo1.maven.org/maven2/xml-apis/xml-apis/1.0.b2/xml-apis-1.0.b2.pom 
Downloading: http://repo1.maven.org/maven2/commons-logging/commons-logging/1.0.4/commons-logging-1.0.4.pom 
Downloading: http://repo1.maven.org/maven2/oro/oro/2.0.8/oro-2.0.8.pom 
Downloading: http://repo1.maven.org/maven2/xml-apis/xml-apis/2.0.2/xml-apis-2.0.2.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/doxia/doxia-core/1.0-alpha-7/doxia-core-1.0-alpha-7.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/doxia/doxia/1.0-alpha-7/doxia-1.0-alpha-7.pom 
Downloading: http://repo1.maven.org/maven2/oro/oro/2.0.7/oro-2.0.7.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/doxia/doxia-sink-api/1.0-alpha-7/doxia-sink-api-1.0-alpha-7.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven-plugin-api/2.0.4/maven-plugin-api-2.0.4.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/reporting/maven-reporting-api/2.0.4/maven-reporting-api-2.0.4.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/doxia/doxia-site-renderer/1.0-alpha-7/doxia-site-renderer-1.0-alpha-7.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-i18n/1.0-beta-6/plexus-i18n-1.0-beta-6.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-components/1.1.4/plexus-components-1.1.4.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-container-default/1.0-alpha-8/plexus-container-default-1.0-alpha-8.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-velocity/1.1.2/plexus-velocity-1.1.2.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-container-default/1.0-alpha-7/plexus-container-default-1.0-alpha-7.pom 
Downloading: http://repo1.maven.org/maven2/plexus/plexus-containers/1.0.2/plexus-containers-1.0.2.pom 
Downloading: http://repo1.maven.org/maven2/plexus/plexus-root/1.0.3/plexus-root-1.0.3.pom 
Downloading: http://repo1.maven.org/maven2/commons-collections/commons-collections/2.0/commons-collections-2.0.pom 
Downloading: http://repo1.maven.org/maven2/commons-logging/commons-logging-api/1.0.4/commons-logging-api-1.0.4.pom 
Downloading: http://repo1.maven.org/maven2/velocity/velocity/1.4/velocity-1.4.pom 
Downloading: http://repo1.maven.org/maven2/velocity/velocity-dep/1.4/velocity-dep-1.4.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/doxia/doxia-decoration-model/1.0-alpha-7/doxia-decoration-model-1.0-alpha-7.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-utils/2.0.5/plexus-utils-2.0.5.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus/2.0.6/plexus-2.0.6.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-archiver/1.0/plexus-archiver-1.0.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-components/1.1.17/plexus-components-1.1.17.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus/2.0.5/plexus-2.0.5.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-io/1.0/plexus-io-1.0.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-container-default/1.5.4/plexus-container-default-1.5.4.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-containers/1.5.4/plexus-containers-1.5.4.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-utils/1.4.5/plexus-utils-1.4.5.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-classworlds/2.2.2/plexus-classworlds-2.2.2.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus/2.0.3/plexus-2.0.3.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/xbean/xbean-reflect/3.4/xbean-reflect-3.4.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/xbean/xbean/3.4/xbean-3.4.pom 
Downloading: http://repo1.maven.org/maven2/log4j/log4j/1.2.12/log4j-1.2.12.pom 
Downloading: http://repo1.maven.org/maven2/commons-logging/commons-logging-api/1.1/commons-logging-api-1.1.pom 
Downloading: http://repo1.maven.org/maven2/com/google/collections/google-collections/1.0/google-collections-1.0.pom 
Downloading: http://repo1.maven.org/maven2/com/google/google/1/google-1.pom 
Downloading: http://repo1.maven.org/maven2/junit/junit/3.8.2/junit-3.8.2.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-component-api/1.0-alpha-32/plexus-component-api-1.0-alpha-32.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-containers/1.0-alpha-32/plexus-containers-1.0-alpha-32.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-classworlds/1.2-alpha-10/plexus-classworlds-1.2-alpha-10.pom 
Downloading: http://repo1.maven.org/maven2/commons-jxpath/commons-jxpath/1.3/commons-jxpath-1.3.pom 
Downloading: http://repo1.maven.org/maven2/commons-io/commons-io/1.4/commons-io-1.4.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/commons/commons-parent/7/commons-parent-7.pom 
Downloading: http://repo1.maven.org/maven2/asm/asm/3.2/asm-3.2.pom 
Downloading: http://repo1.maven.org/maven2/asm/asm-parent/3.2/asm-parent-3.2.pom 
Downloading: http://repo1.maven.org/maven2/commons-lang/commons-lang/2.5/commons-lang-2.5.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/commons/commons-parent/12/commons-parent-12.pom 
Downloading: http://repo1.maven.org/maven2/oro/oro/2.0.7/oro-2.0.7.jar
Downloading: http://repo1.maven.org/maven2/org/apache/maven/doxia/doxia-core/1.0-alpha-7/doxia-core-1.0-alpha-7.jar
Downloading: http://repo1.maven.org/maven2/commons-io/commons-io/1.4/commons-io-1.4.jar
Downloading: http://repo1.maven.org/maven2/org/apache/maven/reporting/maven-reporting-impl/2.0.4/maven-reporting-impl-2.0.4.jar
Downloading: http://repo1.maven.org/maven2/commons-digester/commons-digester/1.6/commons-digester-1.6.jar  
Downloading: http://repo1.maven.org/maven2/commons-validator/commons-validator/1.2.0/commons-validator-1.2.0.jar  
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-utils/2.0.5/plexus-utils-2.0.5.jar 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/shared/file-management/1.1/file-management-1.1.jar
Downloading: http://repo1.maven.org/maven2/commons-lang/commons-lang/2.5/commons-lang-2.5.jar
Downloading: http://repo1.maven.org/maven2/velocity/velocity/1.4/velocity-1.4.jar   
Downloading: http://repo1.maven.org/maven2/org/apache/maven/plugins/maven-dependency-plugin/2.1/maven-dependency-plugin-2.1.jar 
Downloading: http://repo1.maven.org/maven2/commons-logging/commons-logging/1.0.4/commons-logging-1.0.4.jar 
Downloading: http://repo1.maven.org/maven2/commons-beanutils/commons-beanutils/1.7.0/commons-beanutils-1.7.0.jar 
Downloading: http://repo1.maven.org/maven2/asm/asm/3.2/asm-3.2.jar
Downloading: http://repo1.maven.org/maven2/xml-apis/xml-apis/1.0.b2/xml-apis-1.0.b2.jar  
Downloading: http://repo1.maven.org/maven2/commons-jxpath/commons-jxpath/1.3/commons-jxpath-1.3.jar 
Downloading: http://repo1.maven.org/maven2/commons-collections/commons-collections/2.1/commons-collections-2.1.jar 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/doxia/doxia-site-renderer/1.0-alpha-7/doxia-site-renderer-1.0-alpha-7.jar
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-archiver/1.0/plexus-archiver-1.0.jar  
Downloading: http://repo1.maven.org/maven2/velocity/velocity-dep/1.4/velocity-dep-1.4.jar
Downloading: http://repo1.maven.org/maven2/org/apache/maven/shared/maven-shared-io/1.0/maven-shared-io-1.0.jar 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-io/1.0/plexus-io-1.0.jar   
Downloading: http://repo1.maven.org/maven2/org/apache/maven/shared/maven-dependency-analyzer/1.1/maven-dependency-analyzer-1.1.jar
Downloading: http://repo1.maven.org/maven2/org/apache/maven/doxia/doxia-decoration-model/1.0-alpha-7/doxia-decoration-model-1.0-alpha-7.jar   
Downloading: http://repo1.maven.org/maven2/org/apache/maven/shared/maven-dependency-tree/1.2/maven-dependency-tree-1.2.jar 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/shared/maven-common-artifact-filters/1.0/maven-common-artifact-filters-1.0.jar
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-i18n/1.0-beta-6/plexus-i18n-1.0-beta-6.jar 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/shared/maven-plugin-testing-harness/1.1/maven-plugin-testing-harness-1.1.jar  
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-velocity/1.1.2/plexus-velocity-1.1.2.jar 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-component-api/1.0-alpha-32/plexus-component-api-1.0-alpha-32.jar

[INFO] ------------------------------------------------------------------------
[INFO] Building Moneydance
[INFO]    task-segment: [clean]
[INFO] ------------------------------------------------------------------------
Downloading: http://repo1.maven.org/maven2/org/apache/maven/plugins/maven-clean-plugin/2.2/maven-clean-plugin-2.2.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/plugins/maven-plugins/10/maven-plugins-10.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/plugins/maven-clean-plugin/2.2/maven-clean-plugin-2.2.jar 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/plugins/maven-compiler-plugin/2.3.2/maven-compiler-plugin-2.3.2.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/plugins/maven-plugins/18/maven-plugins-18.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven-parent/16/maven-parent-16.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/apache/7/apache-7.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/plugins/maven-compiler-plugin/2.3.2/maven-compiler-plugin-2.3.2.jar 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven-profile/2.0/maven-profile-2.0.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven-model/2.0/maven-model-2.0.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven-artifact-manager/2.0/maven-artifact-manager-2.0.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven-repository-metadata/2.0/maven-repository-metadata-2.0.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven-artifact/2.0/maven-artifact-2.0.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/wagon/wagon-provider-api/1.0-alpha-5/wagon-provider-api-1.0-alpha-5.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/shared/file-management/1.2/file-management-1.2.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/maven-plugin-api/2.0.6/maven-plugin-api-2.0.6.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/shared/maven-shared-io/1.1/maven-shared-io-1.1.pom 
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-utils/1.1/plexus-utils-1.1.pom 
Downloading: http://repo1.maven.org/maven2/org/apache/maven/shared/file-management/1.2/file-management-1.2.jar
Downloading: http://repo1.maven.org/maven2/org/codehaus/plexus/plexus-utils/1.1/plexus-utils-1.1.jar  
Downloading: http://repo1.maven.org/maven2/org/apache/maven/shared/maven-shared-io/1.1/maven-shared-io-1.1.jar

[INFO] [clean:clean {execution: default-clean}]
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESSFUL
[INFO] ------------------------------------------------------------------------
[INFO] Total time: 4 minutes
[INFO] Finished at: Tue Jan 11 22:06:17 CST 2011[INFO] Final Memory: 33M/123M
[INFO] ------------------------------------------------------------------------
```

[^1]: _"Someday" never came, and I no longer recall what I found "toxic" at that time. - Ed._
[^2]: _The original post included a truly ridiculous number of blank lines (nearly one per "downloading" message); While including them definitely emphasized the absurdity at hand, it also metaphorically beat upon a horse which was already quite dead._
