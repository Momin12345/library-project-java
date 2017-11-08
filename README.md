# library-project-java
import java.awt.BorderLayout;
import java.awt.EventQueue;

import javax.swing.JFrame;
import javax.swing.JPanel;
import javax.swing.border.EmptyBorder;
import javax.swing.JLabel;
import javax.swing.JButton;
import javax.swing.JTextArea;
import javax.swing.JTextField;
import java.awt.Font;
import java.awt.Color;
import java.awt.event.ActionListener;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.ObjectInputStream;
import java.io.ObjectOutputStream;
import java.awt.event.ActionEvent;

public class MainGUI extends JFrame {

	private JPanel contentPane;
	private JTextField tb1;
	private JTextField tb2;
	private JTextField tb3;
	private JTextField tb4;
	private JTextField tb5;
	private JTextField tb6;
	private JTextField tm1;
	private JTextField tm2;
	private JTextField tm3;
	private JTextField tm4;
	private JTextField tm5;
	private JTextField tm6;
	private JTextField tm7;
	private JTextField tm8;
	private JTextField tp1;
	private JTextField tp2;
	private JTextField tp3;
	private JTextField tp4;
	private JTextField tp5;
	private JTextField tp6;
	private JTextField tp7;
	private JTextField tp8;
	int counterB,counterM,counterP,indicatorB,indicatorM,indicatorP;
	Books[] b=new Books[10];
	Movies[] m=new Movies[10];
	Paintings[] p=new Paintings[10];

	/**
	 * Launch the application.
	 */
	public static void main(String[] args) {
		EventQueue.invokeLater(new Runnable() {
			public void run() {
				try {
					MainGUI frame = new MainGUI();
					frame.setVisible(true);
				} catch (Exception e) {
					e.printStackTrace();
				}
			}
		});
	}

	/**
	 * Create the frame.
	 */
	public MainGUI() {
		initializeB();
		initializeM();
		initializeP();
		
		
		
		
		setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		setBounds(100, 100, 800, 526);
		contentPane = new JPanel();
		contentPane.setBorder(new EmptyBorder(5, 5, 5, 5));
		setContentPane(contentPane);
		contentPane.setLayout(null);
		
		JPanel p4 = new JPanel();
		p4.setBounds(0, 0, 784, 487);
		contentPane.add(p4);
		p4.setBackground(new Color(255, 255, 0));
		p4.setLayout(null);
		
		JLabel lp1 = new JLabel("Paintings Section");
		lp1.setFont(new Font("Tahoma", Font.BOLD, 30));
		lp1.setBounds(244, 11, 272, 47);
		p4.add(lp1);
		
		JLabel lp2 = new JLabel("Paintings Available");
		lp2.setBounds(560, 81, 97, 14);
		p4.add(lp2);
		
		JTextArea tap = new JTextArea();
		tap.setBounds(519, 99, 182, 338);
		p4.add(tap);
		
		JLabel lp3 = new JLabel("Title");
		lp3.setBounds(63, 81, 46, 14);
		p4.add(lp3);
		
		tp1 = new JTextField();
		tp1.setText("");
		tp1.setBounds(137, 78, 86, 20);
		p4.add(tp1);
		tp1.setColumns(10);
		
		tp2 = new JTextField();
		tp2.setBounds(137, 109, 86, 20);
		p4.add(tp2);
		tp2.setColumns(10);
		
		tp3 = new JTextField();
		tp3.setBounds(137, 140, 86, 20);
		p4.add(tp3);
		tp3.setColumns(10);
		
		tp4 = new JTextField();
		tp4.setBounds(137, 171, 86, 20);
		p4.add(tp4);
		tp4.setColumns(10);
		
		tp5 = new JTextField();
		tp5.setBounds(137, 202, 86, 20);
		p4.add(tp5);
		tp5.setColumns(10);
		
		tp6 = new JTextField();
		tp6.setBounds(137, 233, 86, 20);
		p4.add(tp6);
		tp6.setColumns(10);
		
		tp7 = new JTextField();
		tp7.setBounds(137, 264, 86, 20);
		p4.add(tp7);
		tp7.setColumns(10);
		
		tp8 = new JTextField();
		tp8.setBounds(137, 295, 86, 20);
		p4.add(tp8);
		tp8.setColumns(10);
		
		JLabel lp4 = new JLabel("Author");
		lp4.setBounds(63, 112, 46, 14);
		p4.add(lp4);
		
		JLabel lp5 = new JLabel("Purchase Price");
		lp5.setBounds(63, 143, 46, 14);
		p4.add(lp5);
		
		JLabel lp6 = new JLabel("Asking Price");
		lp6.setBounds(63, 174, 46, 14);
		p4.add(lp6);
		
		JLabel lp7 = new JLabel("Height");
		lp7.setBounds(63, 205, 46, 14);
		p4.add(lp7);
		
		JLabel lp8 = new JLabel("Width");
		lp8.setBounds(63, 236, 46, 14);
		p4.add(lp8);
		
		JLabel lp9 = new JLabel("Media");
		lp9.setBounds(63, 267, 46, 14);
		p4.add(lp9);
		
		JLabel lp10 = new JLabel("Genre");
		lp10.setBounds(63, 298, 46, 14);
		p4.add(lp10);
		
		JButton bp1 = new JButton("Add");
		
		bp1.setBounds(63, 338, 89, 23);
		p4.add(bp1);
		
		JButton bp2 = new JButton("Save");
		
		bp2.setBounds(190, 338, 89, 23);
		p4.add(bp2);
		
		JButton bp5 = new JButton("Back");
		bp5.setBounds(314, 338, 89, 23);
		p4.add(bp5);
		
		JButton bp3 = new JButton("Sell");
		
		bp3.setBounds(63, 387, 89, 23);
		p4.add(bp3);
		
		JButton bp4 = new JButton("Confirm");
		bp4.setBounds(190, 387, 89, 23);
		p4.add(bp4);
		
		JButton bp6 = new JButton("Details");
		bp6.setBounds(314, 387, 89, 23);
		p4.add(bp6);
		
		JButton bp7 = new JButton("Enter");
		bp7.setBounds(420, 387, 89, 23);
		p4.add(bp7);
		p4.setVisible(false);
		lp3.setVisible(false);
		lp4.setVisible(false);
		lp5.setVisible(false);
		lp6.setVisible(false);
		lp7.setVisible(false);
		lp8.setVisible(false);
		lp9.setVisible(false);
		lp10.setVisible(false);
		tp1.setVisible(false);
		tp2.setVisible(false);
		tp3.setVisible(false);
		tp4.setVisible(false);
		tp5.setVisible(false);
		tp6.setVisible(false);
		tp7.setVisible(false);
		tp8.setVisible(false);
		bp2.setVisible(false);
		bp4.setVisible(false);
		bp7.setVisible(false);
		
		JPanel p3 = new JPanel();
		p3.setBounds(0, 0, 784, 487);
		contentPane.add(p3);
		p3.setBackground(new Color(178, 34, 34));
		p3.setLayout(null);
		
		JLabel lm2 = new JLabel("Movies Available");
		lm2.setBounds(571, 86, 112, 14);
		p3.add(lm2);
		
		JLabel lm1 = new JLabel("Movies Section");
		lm1.setFont(new Font("Tahoma", Font.BOLD, 30));
		lm1.setBounds(263, 11, 259, 54);
		p3.add(lm1);
		
		JTextArea tam = new JTextArea();
		tam.setBounds(527, 113, 183, 340);
		p3.add(tam);
		
		JLabel lm3 = new JLabel("Title");
		lm3.setBounds(68, 86, 46, 14);
		p3.add(lm3);
		
		tm1 = new JTextField();
		tm1.setBounds(164, 83, 86, 20);
		p3.add(tm1);
		tm1.setColumns(10);
		
		tm2 = new JTextField();
		tm2.setBounds(164, 115, 86, 20);
		p3.add(tm2);
		tm2.setColumns(10);
		
		tm3 = new JTextField();
		tm3.setBounds(164, 146, 86, 20);
		p3.add(tm3);
		tm3.setColumns(10);
		
		tm4 = new JTextField();
		tm4.setBounds(164, 177, 86, 20);
		p3.add(tm4);
		tm4.setColumns(10);
		
		tm5 = new JTextField();
		tm5.setBounds(164, 208, 86, 20);
		p3.add(tm5);
		tm5.setColumns(10);
		
		tm6 = new JTextField();
		tm6.setBounds(164, 239, 86, 20);
		p3.add(tm6);
		tm6.setColumns(10);
		
		tm7 = new JTextField();
		tm7.setBounds(164, 270, 86, 20);
		p3.add(tm7);
		tm7.setColumns(10);
		
		tm8 = new JTextField();
		tm8.setBounds(164, 301, 86, 20);
		p3.add(tm8);
		tm8.setColumns(10);
		
		JLabel lm4 = new JLabel("Author");
		lm4.setBounds(68, 118, 46, 14);
		p3.add(lm4);
		
		JLabel lm5 = new JLabel("Purchase Price");
		lm5.setBounds(68, 149, 86, 14);
		p3.add(lm5);
		
		JLabel lm6 = new JLabel("Asking Price");
		lm6.setBounds(68, 180, 77, 14);
		p3.add(lm6);
		
		JLabel lm7 = new JLabel("Height");
		lm7.setBounds(68, 211, 46, 14);
		p3.add(lm7);
		
		JLabel lm8 = new JLabel("Width");
		lm8.setBounds(68, 242, 46, 14);
		p3.add(lm8);
		
		JLabel lm9 = new JLabel("Media");
		lm9.setBounds(68, 273, 46, 14);
		p3.add(lm9);
		
		JLabel lm10 = new JLabel("Genre");
		lm10.setBounds(68, 304, 46, 14);
		p3.add(lm10);
		
		JButton bm1 = new JButton("Add");
		
		bm1.setBounds(64, 348, 89, 23);
		p3.add(bm1);
		
		JButton bm2 = new JButton("Save");
		
		bm2.setBounds(189, 348, 89, 23);
		p3.add(bm2);
		
		JButton bm5 = new JButton("Back");
		
		bm5.setBounds(317, 348, 89, 23);
		p3.add(bm5);
		
		JButton bm3 = new JButton("Sell");
		
		bm3.setBounds(64, 402, 89, 23);
		p3.add(bm3);
		
		JButton bm4 = new JButton("Confirm");
		
		bm4.setBounds(189, 402, 89, 23);
		p3.add(bm4);
		
		JButton bm6 = new JButton("Details");
		
		bm6.setBounds(317, 402, 89, 23);
		p3.add(bm6);
		
		JButton bm7 = new JButton("Enter");
		
		bm7.setBounds(428, 402, 89, 23);
		p3.add(bm7);
		p3.setVisible(false);
		lm3.setVisible(false);
		lm4.setVisible(false);
		lm5.setVisible(false);
		lm6.setVisible(false);
		lm7.setVisible(false);
		lm8.setVisible(false);
		lm9.setVisible(false);
		lm10.setVisible(false);
		tm1.setVisible(false);
		tm2.setVisible(false);
		tm3.setVisible(false);
		tm4.setVisible(false);
		tm5.setVisible(false);
		tm6.setVisible(false);
		tm7.setVisible(false);
		tm8.setVisible(false);
		bm2.setVisible(false);
		bm4.setVisible(false);
		bm7.setVisible(false);
		
	
		
		JPanel p2 = new JPanel();
		p2.setBounds(0, 0, 784, 487);
		contentPane.add(p2);
		p2.setBackground(new Color(0, 255, 127));
		p2.setLayout(null);
		
		JLabel lb1 = new JLabel("Books Section");
		lb1.setFont(new Font("Tahoma", Font.BOLD, 30));
		lb1.setBounds(241, 11, 243, 44);
		p2.add(lb1);
		
		JLabel lb2 = new JLabel("Books Available");
		lb2.setBounds(586, 99, 116, 17);
		p2.add(lb2);
		
		JTextArea tab = new JTextArea();
		tab.setBounds(530, 127, 198, 336);
		p2.add(tab);
		
		JLabel lb3 = new JLabel("Title");
		lb3.setBounds(75, 102, 46, 14);
		p2.add(lb3);
		
		tb1 = new JTextField();
		tb1.setBounds(168, 99, 198, 20);
		p2.add(tb1);
		tb1.setColumns(10);
		
		tb2 = new JTextField();
		tb2.setBounds(168, 130, 157, 20);
		p2.add(tb2);
		tb2.setColumns(10);
		
		tb3 = new JTextField();
		tb3.setBounds(168, 161, 86, 20);
		p2.add(tb3);
		tb3.setColumns(10);
		
		tb4 = new JTextField();
		tb4.setBounds(168, 192, 86, 20);
		p2.add(tb4);
		tb4.setColumns(10);
		
		tb5 = new JTextField();
		tb5.setBounds(168, 223, 86, 20);
		p2.add(tb5);
		tb5.setColumns(10);
		
		tb6 = new JTextField();
		tb6.setBounds(168, 254, 86, 20);
		p2.add(tb6);
		tb6.setColumns(10);
		
		JLabel lb4 = new JLabel("Author");
		lb4.setBounds(75, 132, 46, 14);
		p2.add(lb4);
		
		JLabel lb5 = new JLabel("Purchase Price");
		lb5.setBounds(75, 164, 96, 14);
		p2.add(lb5);
		
		JLabel lb6 = new JLabel("Asking Price");
		lb6.setBounds(75, 195, 83, 14);
		p2.add(lb6);
		
		JLabel lb7 = new JLabel("Height");
		lb7.setBounds(75, 226, 46, 14);
		p2.add(lb7);
		
		JLabel lb8 = new JLabel("Width");
		lb8.setBounds(75, 257, 46, 14);
		p2.add(lb8);
		
		JButton bb1 = new JButton("Add");
		
		bb1.setBounds(32, 334, 89, 23);
		p2.add(bb1);
		
		JButton bb2 = new JButton("Save");
		
		bb2.setBounds(148, 334, 89, 23);
		p2.add(bb2);
		
		JButton bb5 = new JButton("Back");
		
		bb5.setBounds(272, 334, 89, 23);
		p2.add(bb5);
		
		JButton bb3 = new JButton("Sell");
		
		bb3.setBounds(32, 373, 89, 23);
		p2.add(bb3);
		
		JButton bb4 = new JButton("Confirm");
		
		bb4.setBounds(148, 373, 89, 23);
		p2.add(bb4);
		
		JButton bb6 = new JButton("Details");
		
		bb6.setBounds(272, 373, 89, 23);
		p2.add(bb6);
		
		JButton bb7 = new JButton("Enter");
		
		bb7.setBounds(395, 373, 89, 23);
		p2.add(bb7);
		p2.setVisible(false);
		lb3.setVisible(false);
		lb4.setVisible(false);
		lb5.setVisible(false);
		lb6.setVisible(false);
		lb7.setVisible(false);
		lb8.setVisible(false);
		tb1.setVisible(false);
		tb2.setVisible(false);
		tb3.setVisible(false);
		tb4.setVisible(false);
		tb5.setVisible(false);
		tb6.setVisible(false);
		bb2.setVisible(false);
		bb4.setVisible(false);
		bb7.setVisible(false);
		
		JPanel p1 = new JPanel();
		p1.setBounds(0, 0, 784, 487);
		contentPane.add(p1);
		p1.setBackground(new Color(0, 191, 255));
		p1.setLayout(null);
		
		JLabel l1 = new JLabel("Main Menu");
		l1.setFont(new Font("Tahoma", Font.BOLD, 30));
		l1.setBounds(282, 35, 195, 56);
		p1.add(l1);
		
		JButton b1 = new JButton("Books");
		
		
		b1.setBounds(106, 261, 89, 86);
		p1.add(b1);
		
		JButton b2 = new JButton("Movies");
		
		b2.setBounds(343, 261, 89, 86);
		p1.add(b2);
		
		JButton b3 = new JButton("Paintings");
		
		b3.setBounds(578, 261, 89, 86);
		p1.add(b3);
		
		JButton b4 = new JButton("Exit");
		
		b4.setBounds(343, 415, 89, 23);
		p1.add(b4);
		
		JLabel l2 = new JLabel("Welcome To My  Program!");
		l2.setFont(new Font("Tahoma", Font.PLAIN, 25));
		l2.setBounds(222, 161, 334, 40);
		p1.add(l2);
		
		b1.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent arg0) 
			{
				p1.setVisible(false);
				p2.setVisible(true);
				LoadB();
			}
		});
		
		b2.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent arg0) 
			{
				p1.setVisible(false);
				p3.setVisible(true);
				LoadM();
			}
		});
		
		b3.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent arg0) 
			{
				p1.setVisible(false);
				p4.setVisible(true);
				LoadP();
			}
		});
		
		b4.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent arg0) 
			{
				System.exit(0);
			}
		});
		
		bb1.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) 
			{
				bb1.setVisible(false);
				bb2.setVisible(true);
				bb3.setVisible(false);
				bb4.setVisible(false);
				bb5.setVisible(false);
				bb6.setVisible(false);
				bb7.setVisible(false);
				lb3.setVisible(true);
				lb4.setVisible(true);
				lb5.setVisible(true);
				lb6.setVisible(true);
				lb7.setVisible(true);
				lb8.setVisible(true);
				tb1.setVisible(true);
				tb2.setVisible(true);
				tb3.setVisible(true);
				tb4.setVisible(true);
				tb5.setVisible(true);
				tb6.setVisible(true);
			}
		});
		bb2.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) 
			{
				bb1.setVisible(true);
				bb2.setVisible(false);
				bb3.setVisible(true);
				bb4.setVisible(false);
				bb5.setVisible(true);
				bb6.setVisible(true);
				bb7.setVisible(false);
				lb3.setVisible(false);
				lb4.setVisible(false);
				lb5.setVisible(false);
				lb6.setVisible(false);
				lb7.setVisible(false);
				lb8.setVisible(false);
				tb1.setVisible(false);
				tb2.setVisible(false);
				tb3.setVisible(false);
				tb4.setVisible(false);
				tb5.setVisible(false);
				tb6.setVisible(false);
			}
		});
		
		bb3.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) 
			{
				bb1.setVisible(false);
				bb2.setVisible(false);
				bb3.setVisible(false);
				bb4.setVisible(true);
				bb5.setVisible(false);
				bb6.setVisible(false);
				bb7.setVisible(false);
				lb3.setVisible(true);
				tb1.setVisible(true);
			}
		});
		
		bb4.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) 
			{
				bb1.setVisible(true);
				bb2.setVisible(false);
				bb3.setVisible(true);
				bb4.setVisible(false);
				bb5.setVisible(true);
				bb6.setVisible(true);
				bb7.setVisible(false);
				lb3.setVisible(false);
				lb4.setVisible(false);
				lb5.setVisible(false);
				lb6.setVisible(false);
				lb7.setVisible(false);
				lb8.setVisible(false);
				tb1.setVisible(false);
				tb2.setVisible(false);
				tb3.setVisible(false);
				tb4.setVisible(false);
				tb5.setVisible(false);
				tb6.setVisible(false);
			}
		});
		bb6.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) 
			{
				bb1.setVisible(false);
				bb2.setVisible(false);
				bb3.setVisible(false);
				bb4.setVisible(false);
				bb5.setVisible(false);
				bb6.setVisible(false);
				bb7.setVisible(true);
				lb3.setVisible(true);
				tb1.setVisible(true);
			}
		});
		bb7.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) 
			{
				bb1.setVisible(true);
				bb2.setVisible(false);
				bb3.setVisible(true);
				bb4.setVisible(false);
				bb5.setVisible(true);
				bb6.setVisible(true);
				bb7.setVisible(false);
				lb3.setVisible(true);
				lb4.setVisible(true);
				lb5.setVisible(true);
				lb6.setVisible(true);
				lb7.setVisible(true);
				lb8.setVisible(true);
				tb1.setVisible(true);
				tb2.setVisible(true);
				tb3.setVisible(true);
				tb4.setVisible(true);
				tb5.setVisible(true);
				tb6.setVisible(true);
			}
		});
		bb5.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) 
			{
				p1.setVisible(true);
				p2.setVisible(false);
				SaveB();
			}
		});
		
		bm1.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent arg0) 
			{
				bm1.setVisible(false);
				bm2.setVisible(true);
				bm3.setVisible(false);
				bm4.setVisible(false);
				bm5.setVisible(false);
				bm6.setVisible(false);
				bm7.setVisible(false);
				lm3.setVisible(true);
				lm4.setVisible(true);
				lm5.setVisible(true);
				lm6.setVisible(true);
				lm7.setVisible(true);
				lm8.setVisible(true);
				lm9.setVisible(true);
				lm10.setVisible(true);
				tm1.setVisible(true);
				tm2.setVisible(true);
				tm3.setVisible(true);
				tm4.setVisible(true);
				tm5.setVisible(true);
				tm6.setVisible(true);
				tm7.setVisible(true);
				tm8.setVisible(true);
			}
		});
		bm2.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent arg0) 
			{
				bm1.setVisible(true);
				bm2.setVisible(false);
				bm3.setVisible(true);
				bm4.setVisible(false);
				bm5.setVisible(true);
				bm6.setVisible(true);
				bm7.setVisible(false);
				lm3.setVisible(false);
				lm4.setVisible(false);
				lm5.setVisible(false);
				lm6.setVisible(false);
				lm7.setVisible(false);
				lm8.setVisible(false);
				lm9.setVisible(false);
				lm10.setVisible(false);
				tm1.setVisible(false);
				tm2.setVisible(false);
				tm3.setVisible(false);
				tm4.setVisible(false);
				tm5.setVisible(false);
				tm6.setVisible(false);
				tm7.setVisible(false);
				tm8.setVisible(false);
			}
		});
		bm3.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent arg0) 
			{
				bm1.setVisible(false);
				bm2.setVisible(false);
				bm3.setVisible(false);
				bm4.setVisible(true);
				bm5.setVisible(false);
				bm6.setVisible(false);
				bm7.setVisible(false);
				lm3.setVisible(true);
				tm1.setVisible(true);
			}
		});
		bm4.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent arg0) {
				bm1.setVisible(true);
				bm2.setVisible(false);
				bm3.setVisible(true);
				bm4.setVisible(false);
				bm5.setVisible(true);
				bm6.setVisible(true);
				bm7.setVisible(false);
				lm3.setVisible(false);
				lm4.setVisible(false);
				lm5.setVisible(false);
				lm6.setVisible(false);
				lm7.setVisible(false);
				lm8.setVisible(false);
				lm9.setVisible(false);
				lm10.setVisible(false);
				tm1.setVisible(false);
				tm2.setVisible(false);
				tm3.setVisible(false);
				tm4.setVisible(false);
				tm5.setVisible(false);
				tm6.setVisible(false);
				tm7.setVisible(false);
				tm8.setVisible(false);
			}
		});
		bm6.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e)
			{
				bm1.setVisible(false);
				bm2.setVisible(false);
				bm3.setVisible(false);
				bm4.setVisible(false);
				bm5.setVisible(false);
				bm6.setVisible(false);
				bm7.setVisible(true);
				lm3.setVisible(true);
				tm1.setVisible(true);
			}
		});
		bm7.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) 
			{
				lm3.setVisible(true);
				lm4.setVisible(true);
				lm5.setVisible(true);
				lm6.setVisible(true);
				lm7.setVisible(true);
				lm8.setVisible(true);
				lm9.setVisible(true);
				lm10.setVisible(true);
				tm1.setVisible(true);
				tm2.setVisible(true);
				tm3.setVisible(true);
				tm4.setVisible(true);
				tm5.setVisible(true);
				tm6.setVisible(true);
				tm7.setVisible(true);
				tm8.setVisible(true);
				bm1.setVisible(true);
				bm2.setVisible(false);
				bm3.setVisible(true);
				bm4.setVisible(false);
				bm5.setVisible(true);
				bm6.setVisible(true);
				bm7.setVisible(false);
			}
		});
		bm5.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent arg0) 
			{
				p1.setVisible(true);
				p3.setVisible(false);
				SaveM();
			}
		});
		bp1.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) 
			{
				bp1.setVisible(false);
				bp2.setVisible(true);
				bp3.setVisible(false);
				bp4.setVisible(false);
				bp5.setVisible(false);
				bp6.setVisible(false);
				bp7.setVisible(false);
				lp3.setVisible(true);
				lp4.setVisible(true);
				lp5.setVisible(true);
				lp6.setVisible(true);
				lp7.setVisible(true);
				lp8.setVisible(true);
				lp9.setVisible(true);
				lp10.setVisible(true);
				tp1.setVisible(true);
				tp2.setVisible(true);
				tp3.setVisible(true);
				tp4.setVisible(true);
				tp5.setVisible(true);
				tp6.setVisible(true);
				tp7.setVisible(true);
				tp8.setVisible(true);	
			}
		});
		bp2.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) 
			{
				bp1.setVisible(true);
				bp2.setVisible(false);
				bp3.setVisible(true);
				bp4.setVisible(false);
				bp5.setVisible(true);
				bp6.setVisible(true);
				bp7.setVisible(false);
				lp3.setVisible(false);
				lp4.setVisible(false);
				lp5.setVisible(false);
				lp6.setVisible(false);
				lp7.setVisible(false);
				lp8.setVisible(false);
				lp9.setVisible(false);
				lp10.setVisible(false);
				tp1.setVisible(false);
				tp2.setVisible(false);
				tp3.setVisible(false);
				tp4.setVisible(false);
				tp5.setVisible(false);
				tp6.setVisible(false);
				tp7.setVisible(false);
				tp8.setVisible(false);
			}
		});
		bp3.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) 
			{
				bp1.setVisible(false);
				bp2.setVisible(false);
				bp3.setVisible(false);
				bp4.setVisible(true);
				bp5.setVisible(false);
				bp6.setVisible(false);
				bp7.setVisible(false);
				lp3.setVisible(true);
				tp1.setVisible(true);	
			}
		});
		bp4.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent arg0) {
				bp1.setVisible(true);
				bp2.setVisible(false);
				bp3.setVisible(true);
				bp4.setVisible(false);
				bp5.setVisible(true);
				bp6.setVisible(true);
				bp7.setVisible(false);
				lp3.setVisible(false);
				lp4.setVisible(false);
				lp5.setVisible(false);
				lp6.setVisible(false);
				lp7.setVisible(false);
				lp8.setVisible(false);
				lp9.setVisible(false);
				lp10.setVisible(false);
				tp1.setVisible(false);
				tp2.setVisible(false);
				tp3.setVisible(false);
				tp4.setVisible(false);
				tp5.setVisible(false);
				tp6.setVisible(false);
				tp7.setVisible(false);
				tp8.setVisible(false);
			}
		});
		bp6.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e)
			{
				bp1.setVisible(false);
				bp2.setVisible(false);
				bp3.setVisible(false);
				bp4.setVisible(false);
				bp5.setVisible(false);
				bp6.setVisible(false);
				bp7.setVisible(true);
				lp3.setVisible(true);
				tp1.setVisible(true);
			}
		});
		bp7.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) 
			{
				lp3.setVisible(true);
				lp4.setVisible(true);
				lp5.setVisible(true);
				lp6.setVisible(true);
				lp7.setVisible(true);
				lp8.setVisible(true);
				lp9.setVisible(true);
				lp10.setVisible(true);
				tp1.setVisible(true);
				tp2.setVisible(true);
				tp3.setVisible(true);
				tp4.setVisible(true);
				tp5.setVisible(true);
				tp6.setVisible(true);
				tp7.setVisible(true);
				tp8.setVisible(true);
				bp1.setVisible(true);
				bp2.setVisible(false);
				bp3.setVisible(true);
				bp4.setVisible(false);
				bp5.setVisible(true);
				bp6.setVisible(true);
				bp7.setVisible(false);
			}
		});
		bp5.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent arg0) 
			{
				p1.setVisible(true);
				p4.setVisible(false);
				SaveP();
			}
		});
	}
	
	void initializeB()
	{
		for(int i=0;i<10;i++)
		{ 
			b[i]=new Books();
	
		}
	}
	
	void initializeM()
	{
		for(int i=0;i<10;i++)
		{ 
			m[i]=new Movies();
	
		}
	}
	
	void initializeP()
	{
		for(int i=0;i<10;i++)
		{ 
			p[i]=new Paintings();
	
		}
	}
	
	void LoadB(){
		try
		{
			FileInputStream fist=new FileInputStream("Books.dat");
			ObjectInputStream oist =new ObjectInputStream(fist);
			for(int i=0;i<10;i++)
			{	
			b[i]=(Books)oist.readObject();
			
			}oist.close();
			
		}catch(Exception e3)
		{
			System.out.println("Exception");
		}
	}
	
	void LoadM(){
		try
		{
			FileInputStream fist=new FileInputStream("Movies.dat");
			ObjectInputStream oist =new ObjectInputStream(fist);
			for(int i=0;i<10;i++)
			{	
			m[i]=(Movies)oist.readObject();
			
			}oist.close();
			
		}catch(Exception e3)
		{
			System.out.println("Exception");
		}
	}
	
	void LoadP(){
		try
		{
			FileInputStream fist=new FileInputStream("Paintings.dat");
			ObjectInputStream oist =new ObjectInputStream(fist);
			for(int i=0;i<10;i++)
			{	
			p[i]=(Paintings)oist.readObject();
			
			}oist.close();
			
		}catch(Exception e3)
		{
			System.out.println("Exception");
		}
	}
	
	void SaveB(){
		try
		{
			FileOutputStream fost=new FileOutputStream("Books.dat");
			ObjectOutputStream oost =new ObjectOutputStream(fost);
			for(int i=0;i<10;i++)
			{oost.writeObject(b[i]);
			}
			oost.close();
			
		}
		catch(Exception e2)
		{
			System.out.println("Exception");
		}
	}
	
	void SaveM(){
		try
		{
			FileOutputStream fost=new FileOutputStream("Movies.dat");
			ObjectOutputStream oost =new ObjectOutputStream(fost);
			for(int i=0;i<10;i++)
			{oost.writeObject(m[i]);
			}
			oost.close();
			
		}
		catch(Exception e2)
		{
			System.out.println("Exception");
		}
	}
	void SaveP(){
		try
		{
			FileOutputStream fost=new FileOutputStream("Paintings.dat");
			ObjectOutputStream oost =new ObjectOutputStream(fost);
			for(int i=0;i<10;i++)
			{oost.writeObject(p[i]);
			}
			oost.close();
			
		}
		catch(Exception e2)
		{
			System.out.println("Exception");
		}
	}
	
}
