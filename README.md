# Calculator
it's a basic calculator program based java gui programming.
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
class calculator extends JFrame implements ActionListener
{
	JButton b1 = new JButton("1");
	JButton b2 = new JButton("2");
	JButton b3 = new JButton("3");
	JButton b4 = new JButton("4");
	JButton b5 = new JButton("5");
	JButton b6 = new JButton("6");
	JButton b7 = new JButton("7");
	JButton b8 = new JButton("8");
	JButton b9 = new JButton("9");
	JButton b0 = new JButton("0");
	JButton plus = new JButton("+");
	JButton sub = new JButton("-");
	JButton mul = new JButton("*");
	JButton div = new JButton("/");
	JButton clear = new JButton("CLR");
	JButton equals = new JButton("=");
	JButton dot = new JButton(".");
	TextField txt = new TextField(15);
	String str_number = "";
	int operation = 0;
	double num1 = 0;
	double num2 = 0;
	double result = 0;
	
	public calculator()
	{
		JFrame frame = new JFrame("JAVA CALCULATOR");
		frame.setVisible(true);
		frame.setResizable(true);
		frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		frame.setSize(400,400);
		
		JPanel Head_Panel = new JPanel();
		JPanel Number_Panel = new JPanel();
		JPanel Result_Panel = new JPanel();
		
		frame.setLayout(new BorderLayout());
		
		Number_Panel.setLayout(new GridLayout(4,4));
		Result_Panel.setLayout(new FlowLayout());
		
		Head_Panel.setBackground(Color.decode("#4797c2"));
		Result_Panel.setBackground(Color.decode("#4797c2"));
		
		JLabel java_cal = new JLabel("JAVA CALCULATOR");
		java_cal.setForeground(Color.WHITE);
		Head_Panel.add(java_cal);
		
		Number_Panel.add(b1);
		b1.addActionListener(this);
		Number_Panel.add(b2);
		b2.addActionListener(this);
		Number_Panel.add(b3);
		b3.addActionListener(this);
		Number_Panel.add(plus);
		plus.addActionListener(this);
		Number_Panel.add(b4);
		b4.addActionListener(this);
		Number_Panel.add(b5);
		b5.addActionListener(this);
		Number_Panel.add(b6);
		b6.addActionListener(this);
		Number_Panel.add(sub);
		sub.addActionListener(this);
		Number_Panel.add(b7);
		b7.addActionListener(this);
		Number_Panel.add(b8);
		b8.addActionListener(this);
		Number_Panel.add(b9);
		b9.addActionListener(this);
		Number_Panel.add(mul);
		mul.addActionListener(this);
		Number_Panel.add(b0);
		b0.addActionListener(this);
		Number_Panel.add(clear);
		clear.addActionListener(this);
		Number_Panel.add(dot);
		dot.addActionListener(this);
		Number_Panel.add(div);
		div.addActionListener(this);
		
		JLabel num = new JLabel("NUMBER :");
		num.setForeground(Color.WHITE);
		Result_Panel.add(num);
		Result_Panel.add(txt);
		Result_Panel.add(equals);
		equals.addActionListener(this);
		txt.setEditable(false);
		
		frame.add(Head_Panel, BorderLayout.NORTH);
		frame.add(Number_Panel, BorderLayout.CENTER);
		frame.add(Result_Panel, BorderLayout.SOUTH);
	}
	
	public void actionPerformed(ActionEvent e)
	{
		if(e.getSource() == b1){
			txt.setText("1");
			str_number += txt.getText();
			txt.setText(str_number);
		}
		else if(e.getSource() == b2){
			txt.setText("2");
			str_number += txt.getText();
			txt.setText(str_number);
		}
		else if(e.getSource() == b3){
			txt.setText("3");
			str_number += txt.getText();
			txt.setText(str_number);
		}
		else if(e.getSource() == b4){
			txt.setText("4");
			str_number += txt.getText();
			txt.setText(str_number);
		}
		else if(e.getSource() == b5){
			txt.setText("5");
			str_number += txt.getText();
			txt.setText(str_number);
		}
		else if(e.getSource() == b6){
			txt.setText("6");
			str_number += txt.getText();
			txt.setText(str_number);
		}
		else if(e.getSource() == b7){
			txt.setText("7");
			str_number += txt.getText();
			txt.setText(str_number);
		}
		else if(e.getSource() == b8){
			txt.setText("8");
			str_number += txt.getText();
			txt.setText(str_number);
		}
		else if(e.getSource() == b9){
			txt.setText("9");
			str_number += txt.getText();
			txt.setText(str_number);
		}
		else if(e.getSource() == b0){
			txt.setText("0");
			str_number += txt.getText();
			txt.setText(str_number);
		}
		else if(e.getSource() == dot){
			txt.setText(".");
			str_number += txt.getText();
			txt.setText(str_number);
		}
		else if(e.getSource() == plus){
			if(operation == 0 & str_number != ""){
				num1 = Double.parseDouble(str_number);
				txt.setText("+");
				str_number += txt.getText();
				txt.setText(str_number);
				operation = 1;
			}
			else{
				txt.setText(str_number);
			}
		}
		else if(e.getSource() == sub){
			if(operation == 0 & str_number != ""){
				num1 = Double.parseDouble(str_number);
				txt.setText("-");
				str_number += txt.getText();
				txt.setText(str_number);
				operation = 2;
			}
			else{
				txt.setText(str_number);
			}
		}
		else if(e.getSource() == mul){
			if(operation == 0 & str_number != ""){
				num1 = Double.parseDouble(str_number);
				txt.setText("*");
				str_number += txt.getText();
				txt.setText(str_number);
				operation = 3;
			}
			else{
				txt.setText(str_number);
			}
		}
		else if(e.getSource() == div){
			if(operation == 0 & str_number != ""){
				num1 = Double.parseDouble(str_number);
				txt.setText("/");
				str_number += txt.getText();
				txt.setText(str_number);
				operation = 4;
			}
			else{
				txt.setText(str_number);
			}
		}
		else if(e.getSource() == equals){
			if(operation != 0 & str_number != ""){
				txt.setText("=");
				str_number += txt.getText();
				txt.setText(str_number);
				switch(operation){
					case 1: {
					     String [] buff = null ;
						 buff = str_number.split("\\+");
						 num2 = Double.parseDouble(buff[1].replace("=", ""));
						 result = num1 + num2 ;
						 txt.setText(str_number + Double.toString(result));
						 break;
					}
					case 2: {
					     String [] buff = null ;
						 buff = str_number.split("\\-");
						 num2 = Double.parseDouble(buff[1].replace("=", ""));
						 result = num1 - num2 ;
						 txt.setText(str_number + Double.toString(result));
						 break;
					}
					case 3: {
					     String [] buff = null ;
						 buff = str_number.split("\\*");
						 num2 = Double.parseDouble(buff[1].replace("=", ""));
						 result = num1 * num2 ;
						 txt.setText(str_number + Double.toString(result));
						 break;
					}
				   case 4: {
					     String [] buff = null ;
						 buff = str_number.split("\\/");
						 num2 = Double.parseDouble(buff[1].replace("=", ""));
						 result = num1 / num2 ;
						 txt.setText(str_number + Double.toString(result));
						 break;
				   }
				}
			b1.setEnabled(false);
			b2.setEnabled(false);
			b3.setEnabled(false);
			b4.setEnabled(false);
			b5.setEnabled(false);
			b6.setEnabled(false);
			b7.setEnabled(false);
			b8.setEnabled(false);
			b9.setEnabled(false);
			b0.setEnabled(false);
			plus.setEnabled(false);
			sub.setEnabled(false);
			mul.setEnabled(false);
			div.setEnabled(false);
			dot.setEnabled(false);
			equals.setEnabled(false);
			}
			else{
				txt.setText("ERROR");
			}
		}
		else if(e.getSource() == clear){
			txt.setText("");
			operation = 0;
			num1 = 0;
			num2 = 0;
			str_number = "";
			result = 0;
			b1.setEnabled(true);
			b2.setEnabled(true);
			b3.setEnabled(true);
			b4.setEnabled(true);
			b5.setEnabled(true);
			b6.setEnabled(true);
			b7.setEnabled(true);
			b8.setEnabled(true);
			b9.setEnabled(true);
			b0.setEnabled(true);
			plus.setEnabled(true);
			sub.setEnabled(true);
			mul.setEnabled(true);
			div.setEnabled(true);
			dot.setEnabled(true);
			clear.setEnabled(true);
			equals.setEnabled(true);
			
		}
	}
	
	public static void main(String args[])
	{
		calculator cal = new calculator();
	}
}
