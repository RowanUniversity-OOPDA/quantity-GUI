quantity-GUI
============
import java.awt.BorderLayout;


public class quantity extends JFrame {

	private JPanel contentPane;
	/**
	 * @wbp.nonvisual location=19,-29
	 */
	private final JLabel label = new JLabel("New label");
	private JTextField textField;

	/**
	 * Launch the application.
	 */
	public static void main(String[] args) {
		EventQueue.invokeLater(new Runnable() {
			public void run() {
				try {
					quantity frame = new quantity();
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
	public quantity() {
		setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		setBounds(100, 100, 450, 300);
		contentPane = new JPanel();
		contentPane.setBorder(new EmptyBorder(5, 5, 5, 5));
		setContentPane(contentPane);
		contentPane.setLayout(null);
		
		JLabel lblHowManyTickets = new JLabel("How many Tickets would you like to buy?");
		lblHowManyTickets.setBounds(82, 36, 295, 16);
		contentPane.add(lblHowManyTickets);
		
		textField = new JTextField();
		textField.setBounds(147, 64, 134, 28);
		contentPane.add(textField);
		textField.setColumns(10);
		
		final JCheckBox check = new JCheckBox("Use free tickets if eligable");
		check.setBounds(57, 126, 214, 28);
		contentPane.add(check);
		
		JButton btnContinueToCheck = new JButton("Continue to check out");
		btnContinueToCheck.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				int d = Integer.parseInt(textField.getText());
				welcome.tm.quantity = d;
				welcome.tm.usefree = check.isSelected(); 
				System.exit(0);
			}
		});
		btnContinueToCheck.setBounds(120, 190, 213, 28);
		contentPane.add(btnContinueToCheck);
	}
}
