1. 生成pdf

`//Step 1—Create a Document.`

`Document document = new Document();`

`//Step 2—Get a PdfWriter instance.`

`PdfWriter.getInstance(document, new FileOutputStream(FILE_DIR + "createSamplePDF.pdf"));`

`//Step 3—Open the Document.`

`document.open();`

`//Step 4—Add content.  `

`document.add(new Paragraph("Hello World"));  `

`//Step 5—Close the Document.  `

`document.close();`

2. 