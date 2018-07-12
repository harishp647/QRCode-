# QRCode 
   public static void main(String[] args) throws Exception {
        String details = "HarishPindi linked In: https://www.linkedin.com/in/harish-pindi-4826a5a8/";
        // first we need to create object of out(which belongs to package java.io) because of this class we can create image here//
        ByteArrayOutputStream out = QRCode.from(details).to(ImageType.JPG).stream();
        // Once we got this outstream , we need a file where we can write this code//
        File f = new File("C:\\Users\\harishp647\\Desktop\\printouts\\New folder\\MyChannel.jpg");
        // Once we got the file object we need file output stream, which helps to write data in to the file
        
        FileOutputStream fos = new FileOutputStream(f);
        fos.write(out.toByteArray());
        // in order to wite data in to file these write fn only takes array of bytes 
        // In order to take array of bytes we need to pass (out.toByteArray()) which will convert bytes to array.
        fos.flush();
