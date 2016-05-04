package javaapplication28;

import java.util.Deque;
import java.util.LinkedList;

/**
 *
 * @author Artur
 */
public class JavaApplication28 {

    /**
     * @param args the command line arguments
     */
    //Zad 3
    public static void main(String[] args) {
       String lastString = "";
char[] result = new char[lastString.length() / 8];
for (int i = 0; i < lastString.length(); i += 8) {
    String sub = lastString.substring(i, i + 8);
    result[i / 8] = (char) Integer.parseInt(sub, 2);
}
System.out.println(new String(result));
    }
    
}
 //zad1
 String input = "";

    int parents = 0;
    Deque<Character> deque = new LinkedList<>();
    for (char c : input.toCharArray()) {
        switch (c) {
            case '(':
                deque.addLast(c);
                break;
            case ')':
                deque.removeLast();
                if (deque.isEmpty()) {
                    parents++;
                }
                break;
        }
    }
    System.out.printf("Parents: %d", parents);
}
}
//zad2
String question;
        int answer;

        question = "1+7/4";

        ScriptEngineManager mgr = new ScriptEngineManager();
        ScriptEngine engine = mgr.getEngineByName("JavaScript");

        answer = ((Number)engine.eval(question)).intValue();
        System.out.println(answer);
       }
}

//zad5
 public class Mailbox
005: {
006:    /**
007:       Creates Mailbox object.
008:       @param aPasscode passcode number
009:       @param aGreeting greeting string
010:    */
011:    public Mailbox(String aPasscode, String aGreeting)
012:    {
013:       passcode = aPasscode;
014:       greeting = aGreeting;
015:       newMessages = new MessageQueue();
016:       keptMessages = new MessageQueue();
017:    }
018: 
019:    /**
020:       Check if the passcode is correct.
021:       @param aPasscode a passcode to check
022:       @return true if the supplied passcode matches the mailbox passcode
023:    */
024:    public boolean checkPasscode(String aPasscode)
025:    {
026:       return aPasscode.equals(passcode);
027:    }
028: 
029:    /**
030:       Add a message to the mailbox.
031:       @param aMessage the message to be added
032:    */
033:    public void addMessage(Message aMessage)
034:    {
035:       newMessages.add(aMessage);
036:    }
037: 
038:    /**
039:       Get the current message.
040:       @return the current message
041:    */
042:    public Message getCurrentMessage()
043:    {
044:       if (newMessages.size() > 0)
045:          return newMessages.getFirst();
046:       else if (keptMessages.size() > 0)
047:          return keptMessages.getFirst();
048:       else
049:          return null;
050:    }
051: 
052:    /**
053:       Remove the current message from the mailbox.
054:       @return the message that has just been removed
055:    */
056:    public Message removeCurrentMessage()
057:    {
058:       if (newMessages.size() > 0)
059:          return newMessages.removeFirst();
060:       else if (keptMessages.size() > 0)
061:          return keptMessages.removeFirst();
062:       else
063:          return null;
064:    }
065: 
066:    /**
067:       Save the current message
068:    */
069:    public void saveCurrentMessage()
070:    {
071:       Message m = removeCurrentMessage();
072:       if (m != null)
073:          keptMessages.add(m);
074:    }
075: 
076:    /**
077:       Change mailbox's greeting.
078:       @param newGreeting the new greeting string
079:    */
080:    public void setGreeting(String newGreeting)
081:    {
082:       greeting = newGreeting;
083:    }
084: 
085:    /**
086:       Change mailbox's passcode.
087:       @param newPasscode the new passcode
088:    */
089:    public void setPasscode(String newPasscode)
090:    {
091:       passcode = newPasscode;
092:    }
093: 
094:    /**
095:       Get the mailbox's greeting.
096:       @return the greeting
097:    */
098:    public String getGreeting()
099:    {
100:       return greeting;
101:    }
102: 
103:    private MessageQueue newMessages;
104:    private MessageQueue keptMessages;
105:    private String greeting;
106:    private String passcode;
107: }
