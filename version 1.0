import java.util.*;
import javax.swing.*;
import java.awt.*;
import java.lang.reflect.Constructor;
public class DynamicClassLoadingExample {
	public static void launch(JFrame frame) {
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setPreferredSize(new Dimension(300,300));
        frame.pack();
        frame.setVisible(true);
	}
    public static void main(String[] args) {
    	JFrame frame=new JFrame();
    	launch(frame);
        Scanner scanner = new Scanner(System.in);
        String className="initial";
        while(true) {
        	System.out.print("请输入要加载的类名：");
        	className = scanner.nextLine();
        	if(className.equals("stop")) {
        		break;
        	};
        try {
            Class<?> dynamicClass = Class.forName(className);
            Constructor<?> constructor = dynamicClass.getDeclaredConstructor();
            Object instance =constructor.newInstance();
            System.out.println("成功加载类：" + dynamicClass.getName());
            System.out.println("创建的实例对象：" + instance);
            if( instance instanceof JButton) {
            	((JButton) instance).setText("A Button");
            	frame.add((JButton)instance,BorderLayout.NORTH);
            }else if(instance instanceof JTextArea) {
            	frame.add((JTextArea)instance,BorderLayout.SOUTH);
            }else if(instance instanceof JTextField) {
            	frame.add((JTextField)instance,BorderLayout.WEST);
            }else if(instance instanceof JLabel){
            	((JLabel) instance).setText("A label");
            
            	frame.add((JLabel)instance,BorderLayout.CENTER);
            }else {
            	System.err.println("Wait,please.");
            }
        } catch (Exception e) {
            e.printStackTrace();
        }
        }System.out.println("Thanks for your use.");
        
    }
}
