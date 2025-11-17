import java.io.*;
import java.net.*;

public class Server {
    public static void main(String[] args) throws Exception {
        ServerSocket ss = new ServerSocket(5000);
        System.out.println("Server started. Waiting for client...");
        Socket s = ss.accept();
        System.out.println("Client connected.");

        BufferedReader in = new BufferedReader(new InputStreamReader(s.getInputStream()));
        PrintWriter out = new PrintWriter(s.getOutputStream(), true);
        BufferedReader keyboard = new BufferedReader(new InputStreamReader(System.in));

        String msgIn = "", msgOut = "";

        while (true) {
            msgIn = in.readLine();
            if (msgIn == null || msgIn.equalsIgnoreCase("exit")) {
                System.out.println("Client ended the chat.");
                break;
            }
            System.out.println("Client: " + msgIn);

            System.out.print("Server: ");
            msgOut = keyboard.readLine();
            out.println(msgOut);

            if (msgOut.equalsIgnoreCase("exit")) {
                System.out.println("Chat ended by server.");
                break;
            }
        }

        s.close();
        ss.close();
    }
}
--------------------------------------------

client code

import java.io.*;
import java.net.*;

public class Client {
    public static void main(String[] args) throws Exception {
        Socket s = new Socket("localhost", 5000);
        System.out.println("Connected to server.");

        BufferedReader in = new BufferedReader(new InputStreamReader(s.getInputStream()));
        PrintWriter out = new PrintWriter(s.getOutputStream(), true);
        BufferedReader keyboard = new BufferedReader(new InputStreamReader(System.in));

        String msgIn = "", msgOut = "";

        while (true) {
            System.out.print("Client: ");
            msgOut = keyboard.readLine();
            out.println(msgOut);

            if (msgOut.equalsIgnoreCase("exit")) {
                System.out.println("Chat ended by client.");
                break;
            }

            msgIn = in.readLine();
            if (msgIn == null || msgIn.equalsIgnoreCase("exit")) {
                System.out.println("Server ended the chat.");
                break;
            }
            System.out.println("Server: " + msgIn);
        }

        s.close();
    }
}


============================================================================


strraming audoi and vedio 

ffmpeg -stream_loop -1 -re -i sample.mp4 -c copy -f mpegts udp://127.0.0.1:1234
add @ in vlc url page 
