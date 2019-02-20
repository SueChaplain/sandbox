
# Oracle JDK / OpenJDK differences

The following table illustrates the proprietary components that can be found in an Oracle JDK 8 and the alternative technologies that are either planned or available to replace them. Click on the links to learn more.

| Oracle JDK 8 proprietary component         | Alternative component             | OpenJDK 8 | OpenJDK 11 |
|--------------------------------------------|-----------------------------------|-----------|-----------|
| webstart/browser plugin                    | [IcedTea-Web](#icedtea-web)       | :x: (coming soon)          | :x: (coming soon)  |
| JavaFX                                     | [OpenJFX](#openjfx)               |  :x:           | :heavy_check_mark: (coming soon) |
| T2K font rendering engine                  | [Freetype](#freetype-font-rendering-library)|:heavy_check_mark: | :heavy_check_mark: |
| Monotype Lucida fonts                      | [Relicensed Lucida fonts](#relicensed-lucida-fonts)|  :x: (coming soon)  | :x: (coming soon)  |
| Ductus 2D renderer                         | [Pisces/Marlin](#Pisces-and-marlin) | :heavy_check_mark: (Pisces) | :heavy_check_mark: (Marlin) |
| Kodac Color Matching System (KCMS) library | [LCMS](#lcms)                     | :heavy_check_mark: | :heavy_check_mark: |
| SNMP                                       | Use [JMX](#jmx) (or SNMP4J)           | :heavy_check_mark: (not bundled)  | :heavy_check_mark: (not bundled)  |
| sound drivers                              | Use [Windows sound drivers](#windows-sound-drivers)|:heavy_check_mark: (not bundled)  | :heavy_check_mark: (not bundled)  |
| Java Flight Recorder (JFR)                 | [Java Flight Recorder](#java-flight-recorder)| :x: (coming soon) |  :heavy_check_mark: |
| Java Mission Control (JMC)                 | Use [JDK Mission Control](#jdk-mission-control)| :x: (coming soon) | :x: (coming soon) |

:pencil: JavaFX, JFR, and JMC were all contributed by Oracle to the OpenJDK project for releases after Java 8.

## IcedTea-Web

AdoptOpenJDK are working on a project to provide IcedTea-web as an open source replacement for Webstart and Java plugin technology. This feature
will be available via an installer option in AdoptOpenJDK binaries.


## OpenJFX

Back in 2017, JavaFX was decoupled from the Oracle JDK and contributed to the OpenJDK community. The OpenJFX community is focused on OpenJFX 11+ and AdoptOpenJDK is working with the OpenJFX community to provide it via an installer option in AdoptOpenJDK binaries.

:pencil: OpenJFX 8 is no longer being actively maintained. If you need this capability, we recommend upgrading to OpenJFX 11.

## Freetype font rendering library

OpenJDK uses the open source FreeType font rendering library instead of the proprietary T2K font library.

## Relicensed Lucida fonts

The Lucida fonts that are available in Oracle JDK 8 have a proprietary 3rd party license. AdoptOpenJDK intend to provide relicensed Lucida fonts. Work is ongoing to minimize any display issues when these fonts are rendered by Freetype and is expected to complete in 2Q 2019.

## Pisces and Marlin

Oracle JDK 8 uses a proprietary 2D graphics renderer called Ductus, whereas OpenJDK uses an open-source renderer called Pisces. From OpenJDK 9,
the Marlin renderer is in use. Work is planned at AdoptOpenJDK to either backport Marlin to OpenJDK 8 and/or minimize any display issues between the two. The outlook for completion is Q2 2019.

## LCMS

OpenJDK uses the Little Color Matching System (LCMS) open source open source library instead of the proprietary Kodac CMS library.

## JMX

The proprietary SNMP package shipped with Oracle JDK 8 is not present in OpenJDK. Use JMX as an alternative, or SNMP4J. These packages are
not bundled with the AdoptOpenJDK binaries.

## Windows sound drivers

Oracle JDK provides native sound drivers for Java 8 on Windows, which are not present in OpenJDK. Use the sound drivers that are available
with Microsoft Windows instead.

## Java Flight Recorder

Java Flight Recorder (JFR) was decoupled from the Oracle JDK and contributed to the OpenJDK community. Work is underway to backport JFR from OpenJDK 11 to OpenJDK 8. When this work is complete, AdoptOpenJDK will include JFR in OpenJDK 8 binaries.

## JDK Mission Control

Java Mission Control (JMC) is being open sourced under the OpenJDK [JDK Mission Control project](https://github.com/JDKMissionControl/jmc). When
available, JMC will be able to receive JFR events from OpenJDK 11 and eventually OpenJDK 8, when that backport is complete.  
