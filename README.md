# JavaWuerfelProject

// Code for the Programm
// First Class(Fachklasse):


public class Aufgabe2 {

	public int roll() {
		return (int) (Math.random() * 6)+ 1;
	}
	
	public static void main(String[]agrs) {
		Aufgabe2 Fachklasse = new Aufgabe2();
		System.out.println(Fachklasse.roll());
	}
}



// Second Class (Starter and GUI Class):


import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JLabel;



public class Dice1GUI extends JFrame implements ActionListener {
	
	public static void main(String [] args) {
	Dice1GUI gui = new Dice1GUI();
	gui.showDialog();
	}
	JLabel titleLabel = new JLabel("1 dice roll simulation");
	JLabel awnser = new JLabel("");
	JButton rollButton = new JButton("simulate roll");
	
	Aufgabe2 Fachklasse = new Aufgabe2();
	
	public void showDialog() {
		setLayout(null);
		
		titleLabel.setBounds(10,20,200,20);
		awnser.setBounds(10,80,30,20);
		rollButton.setBounds(10,200,200,30);
		
		add(titleLabel);
		add(awnser);
		add(rollButton);
		
		rollButton.addActionListener(this);
		
		setDefaultCloseOperation(EXIT_ON_CLOSE);
		setSize(300,300);
		setTitle("WürfelProgramm");
		setVisible(true);
	}

	@Override
	public void actionPerformed(ActionEvent agr0) {
		awnser.setText(Integer.toString(Fachklasse.roll()));
	}

}
