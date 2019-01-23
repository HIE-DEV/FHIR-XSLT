# FHIR-XSLT
For providing XSLT files that can transform FHIR messages

**Foreword:**

**It's recommended to have a local copy of the XSLT files found in the XSLT folder on your own service or server, and modify the suggested command lines accordingly to reference the local copies, as this account or files could go down or be changed.**

### Instructions:

To utilise the files for testing of FHIR .XML messages and how they render in HTML, in your .XML document, find the line that contains the XML version (which if you don't have it, should be included; it's usually on the very first line), it will typically look like:

    <?xml version="1.0" encoding="UTF-8"?>

It's after that line you will put one of the following lines of code (depending on what type of FHIR message type you have):

### For ITK3 FHIR messages:

Put the following line (the XSLT assumes that the FHIR bundle containing the Composition is found in the fourth 'entry' of the IKT3 FHIR message):

    <?xml-stylesheet type="text/xsl" href="https://raw.githubusercontent.com/HIE-DEV/FHIR-XSLT/master/XSLT/itk3-fhir-to-html.xsl" ?>

### For FHIR bundles:

Put the following line (the XSLT assumes that the Composition is found in the first entry in the bundle):

    <?xml-stylesheet type="text/xsl" href="https://raw.githubusercontent.com/HIE-DEV/FHIR-XSLT/master/XSLT/fhir-itk3-to-html.xsl" ?>
    
### Modifying for local copies:

If you wish to modify the line of code to point to a local copy of the file, then change the part found in href. For files found physically on a drive, the location is *relative* to where the .XML is located (so for example, href="fhir-itk3-to-html.xsl" would mean the XSLT is in the same directory as the .XML).

### Testing:

Once you've added the line of code of the .XML and saved, simply open the .XML in any reasonably modern browser, and it should render it to HTML.
