# kargo.proje

{                                         
        
        String a = jTextField1.getText();
        char[] b = jPasswordField1.getPassword();
        String c = "";
        
        for (int i = 0; i < b.length; i++) {
            c += b[i];
        }
        
        if (a.equals("admin") && c.equals("1234")) {         
            siparis pencere = new siparis();
            pencere.setVisible(true);
            this.setVisible(false);
        }
        else {
            //JOptionPane.showMessageDialog(null, "Yanlış ID veya şifre girildi.");
            JOptionPane.showMessageDialog(null, "Yanlış kullanıcı adı veya şifre girildi.");
        }
        package javaapplication5;
        import java.util.Random;
        import java.time.LocalTime;
        public class siparis extends javax.swing.JFrame {
    public static Random rand = new Random();
    public static int mah[][] = new int [4][4];
    boolean a = false;
    int sure, paket;
    

    public siparis() {
        initComponents(); 
    }

    siparis(String sipariş) {
        throw new UnsupportedOperationException("Not supported yet."); // Generated from nbfs://nbhost/SystemFileSystem/Templates/Classes/Code/GeneratedMethodBody
        
    }
    private void jButton1ActionPerformed(java.awt.event.ActionEvent evt) {                                         
          if (a == false) {
            for (int i = 0; i < 4; i++) {
             for (int d = 0;  d < 4; d++) {
                 mah[i][d] = rand.nextInt(50)+4;  
                 }
            }
            a = true;
          }
          list1.add(jComboBox1.getSelectedItem().toString() + " " + jComboBox4.getSelectedItem().toString() + " " + jComboBox2.getSelectedItem().toString() + " Mahallesi");
          int hesap = mah[jComboBox4.getSelectedIndex()][jComboBox2.getSelectedIndex()] * 4;
          LocalTime time = LocalTime.parse(jComboBox3.getSelectedItem().toString());
          paket += mah[jComboBox4.getSelectedIndex()][jComboBox2.getSelectedIndex()]; sure += hesap; 
          list2.add("Paket Sayısı: " + mah[jComboBox4.getSelectedIndex()][jComboBox2.getSelectedIndex()] + " Başlama Saati:" + time.toString() + " Bitirme Saati: " + time.plusMinutes(hesap).toString());
          jLabel5.setText("Toplam Paket: " + paket);
          jLabel6.setText("Toplam Süre: " + sure);
    }                                        
