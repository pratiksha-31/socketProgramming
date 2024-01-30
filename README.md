package socket;
import java.io.*;  
import java.net.*;  
public class MyServer {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		try{  
			ServerSocket ss=new ServerSocket(6661);  
			Socket s=ss.accept();//establishes connection   
			DataInputStream dis=new DataInputStream(s.getInputStream());  
			String  str=(String)dis.readUTF();  
			System.out.println("message= "+str);  
			ss.close();  
			}catch(Exception e){System.out.println(e);}  
	}

}



package socket;
import java.io.*;  
import java.net.*;  
public class MyClient {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		try{      
			Socket s=new Socket("localhost",6661);  
			DataOutputStream dout=new DataOutputStream(s.getOutputStream());  
			dout.writeUTF("Hello Server");  
			dout.flush();  
			dout.close();  
			s.close();  
			}catch(Exception e){System.out.println(e);}  
	}

}
