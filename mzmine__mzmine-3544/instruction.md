# Issue

**Title:** Introduced limit in JDK24 prevents import of large mzml files

## Description

The introduced fix allowed me to import large MALDI FT-ICR file. Before I got the following error:
Sep 27, 2026 1:22:05 PM io.github.mzmine.modules.io.import_rawdata_imzml.ImzMLImportTask run
WARNING: Error in imzML import: JAXP00010003: The length of entity "[xml]" is "100,001" that exceeds the "100,000" limit set by "jdk.xml.maxGeneralEntitySizeLimit".
com.alanmrace.jimzmlparser.exceptions.ImzMLParseException: JAXP00010003: The length of entity "[xml]" is "100,001" that exceeds the "100,000" limit set by "jdk.xml.maxGeneralEntitySizeLimit".
	at com.alanmrace.jimzmlparser.parser.ImzMLHandler.parseimzML(ImzMLHandler.java:212)
	at com.alanmrace.jimzmlparser.parser.ImzMLHandler.parseimzML(ImzMLHandler.java:156)
	at com.alanmrace.jimzmlparser.parser.ImzMLHandler.parseimzML(ImzMLHandler.java:140)
	at io.github.mzmine.modules.io.import_rawdata_imzml.ImzMLImportTask.run(ImzMLImportTask.java:132)
	at io.github.mzmine.taskcontrol.impl.WrappedTask.run(WrappedTask.java:169)
	at io.github.mzmine.taskcontrol.threadpools.ThreadPoolTask.lambda$trackProgressTask$0(ThreadPoolTask.java:185)
	at java.base/java.util.concurrent.Executors$RunnableAdapter.call(Executors.java:545)
	at java.base/java.util.concurrent.FutureTask.run(FutureTask.java:330)
	at java.base/java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1090)
	at java.base/java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:614)
	at java.base/java.lang.Thread.run(Thread.java:1516)
Caused by: org.xml.sax.SAXParseException; lineNumber: 600111; columnNumber: 171; JAXP00010003: The length of entity "[xml]" is "100,001" that exceeds the "100,000" limit set by "jdk.xml.maxGeneralEntitySizeLimit".
	at java.xml/com.sun.org.apache.xerces.internal.util.ErrorHandlerWrapper.createSAXParseException(ErrorHandlerWrapper.java:204)
	at java.xml/com.sun.org.apache.xerces.internal.util.ErrorHandlerWrapper.fatalError(ErrorHandlerWrapper.java:178)
	at java.xml/com.sun.org.apache.xerces.internal.impl.XMLErrorReporter.reportError(XMLErrorReporter.java:400)
	at java.xml/com.sun.org.apache.xerces.internal.impl.XMLErrorReporter.reportError(XMLErrorReporter.java:327)
	at java.xml/com.sun.org.apache.xerces.internal.impl.XMLScanner.reportFatalError(XMLScanner.java:1465)
	at java.xml/com.sun.org.apache.xerces.internal.impl.XMLScanner.checkEntityLimit(XMLScanner.java:1536)
	at java.xml/com.sun.org.apache.xerces.internal.impl.XMLScanner.resolveCharacter(XMLScanner.java:1034)
	at java.xml/com.sun.org.apache.xerces.internal.impl.XMLScanner.scanAttributeValue(XMLScanner.java:917)
	at java.xml/com.sun.org.apache.xerces.internal.impl.XMLDocumentFragmentScannerImpl.scanAttribute(XMLDocumentFragmentScannerImpl.java:1532)
	at java.xml/com.sun.org.apache.xerces.internal.impl.XMLDocumentFragmentScannerImpl.scanStartElement(XMLDocumentFragmentScannerImpl.java:1372)
	at java.xml/com.sun.org.apache.xerces.internal.impl.XMLDocumentFragmentScannerImpl$FragmentContentDriver.next(XMLDocumentFragmentScannerImpl.java:2736)
	at java.xml/com.sun.org.apache.xerces.internal.impl.XMLDocumentScannerImpl.next(XMLDocumentScannerImpl.java:635)
	at java.xml/com.sun.org.apache.xerces.internal.impl.XMLDocumentFragmentScannerImpl.scanDocument(XMLDocumentFragmentScannerImpl.java:551)
	at java.xml/com.sun.org.apache.xerces.internal.parsers.XML11Configuration.parse(XML11Configuration.java:890)
	at java.xml/com.sun.org.apache.xerces.internal.parsers.XML11Configuration.parse(XML11Configuration.java:826)
	at java.xml/com.sun.org.apache.xerces.internal.parsers.XMLParser.parse(XMLParser.java:137)
	at java.xml/com.sun.org.apache.xerces.internal.parsers.AbstractSAXParser.parse(AbstractSAXParser.java:1225)
	at java.xml/com.sun.org.apache.xerces.internal.jaxp.SAXParserImpl$JAXPSAXParser.parse(SAXParserImpl.java:629)
	at java.xml/com.sun.org.apache.xerces.internal.jaxp.SAXParserImpl.parse(SAXParserImpl.java:328)
	at java.xml/javax.xml.parsers.SAXParser.parse(SAXParser.java:197)
	at com.alanmrace.jimzmlparser.parser.ImzMLHandler.parseimzML(ImzMLHandler.java:206)
	... 10 more

Sep 27, 2026 1:22:05 PM io.github.mzmine.taskcontrol.impl.WrappedTask run
SEVERE: Error of task Importing data: Error parsing imzML: com.alanmrace.jimzmlparser.exceptions.ImzMLParseException: JAXP00010003: The length of entity "[xml]" is "100,001" that exceeds the "100,000" limit set by "jdk.xml.maxGeneralEntitySizeLimit". (ImzMLHandler.java:212)
Sep 27, 2026 1:22:05 PM io.github.mzmine.taskcontrol.impl.WrappedTask run
SEVERE: Error of task Opening file /Users/aiden/Downloads/20191113_MS55_Sludge_gran_sec1_150_1200_SDHB_pos_A24_20um_304x213.imzML: Error parsing imzML: com.alanmrace.jimzmlparser.exceptions.ImzMLParseException: JAXP00010003: The length of entity "[xml]" is "100,001" that exceeds the "100,000" limit set by "jdk.xml.maxGeneralEntitySizeLimit". (ImzMLHandler.java:212)

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `1abe9b2449bd`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.