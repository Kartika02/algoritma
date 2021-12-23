# algoritma
package pertemuan11;
import java.io.*;
public class tugas {
    static BufferedReader input = new BufferedReader(new InputStreamReader(System.in));
    
    static Boolean jawab = true;
    static String tanya, noKaryawan;
    static int no=0, a=0, b;
                
    static int subtot=0;
    static int subtot1=0;
    static int subtot2=0;
    static int subtot3=0;
    static int subtot4=0;
                
    static int grantot = 0;
    static int grantot1 =0;
    static int grantot2 = 0;
    static int grantot3 = 0;
    static int grantot4 = 0;
    
    static int[] gajipokok = {7500000,6000000,4000000,2000000};
    
    static String[] nmkrywn = new String[100];
    static int[] jumlahAnak = new int[100];
    static int[] kodejabatan = new int[100];
    static int[] kodestatus = new int[100];
    
    static String[] status = new String[100];
    static String[] jbtn = new String[100];
    static int[] gp = new int[100];
    static int[] tunjanganKel = new int[100];
    static int[] tunjanganAnak = new int[100];
    static int[] pph = new int[100];
    static int[] gajiBersih = new int[100];
   
    static void header(){
            
        System.out.println ("------------------------------------------------------------------------------------------------------------------------------------");
        System.out.println ("|    |                |            |                |            |        TUNJANGAN          |                 |                   |");
        System.out.println ("| NO |      NAMA      |   JABATAN  |   GAJI POKOK   |   STATUS   |---------------------------|       PPH       |    GAJI BERSIH    |");
        System.out.println ("|    |                |            |                |            |   KELUARGA  |     ANAK    |                 |                   |");
        System.out.println ("|----|----------------|------------|----------------|------------|-------------|-------------|-----------------|-------------------|");
        }
    
    static void data(int nomer, String nama, String jbtn, int gpok, String stts, int k, int a, int pph, int gber){
            System.out.printf ("|%-4s|%-16s|%-12s|%-16s|%-12s|%-13s|%-13s|%-17s|%-19s|\n", nomer,nama,jbtn,gpok,stts,k,a,pph,gber);
        }
   
    static void subtotal(int subgp, int subtk, int subta, int subpph, int subgber){
            System.out.println("----------------------------------------------------------------------------------------------------------------------------------|");
            System.out.printf ("|%-4s|%-29s|%-16s|%-12s|%-13s|%-13s|%-17s|%-19s|\n", " ", "Sub Total Halaman ini", " "+subgp, " ", " "+subtk, " "+subta, " "+subpph, " "+subgber);
            System.out.println("----------------------------------------------------------------------------------------------------------------------------------|");
        }
   
    static void grandtotal(int gratotgp, int gratotk, int gratota, int gratotpph, int gratotgber){
            System.out.println("----------------------------------------------------------------------------------------------------------------------------------|");
            System.out.printf ("|%-4s|%-29s|%-16s|%-12s|%-13s|%-13s|%-17s|%-19s|\n", " ", "Total Keseluruhan", " "+gratotgp, " ", " "+gratotk, " "+gratota, " "+gratotpph, " "+gratotgber);
            System.out.println("----------------------------------------------------------------------------------------------------------------------------------|");
        }
        
    static int jumlah_tunjangan_keluarga (int stts, int gpok) {
        int tk;
        if (stts==2) {tk=gpok*10/100;}
        else {tk=0;}
        return tk;
        }
    
    static int jumlah_tunjangan_anak (int jumanak, int gpok) {
        int ta;
        ta=gpok*jumanak*5/100;
        return ta;
        }
    
    static int jumlah_pph (int gpok) {
        int pph;
        pph=gpok*25/1000;
        return pph;
        }
    
public static void main(String[] args)throws IOException{
   
    for (int a=0; a<data; a++) {
            System.out.print ("Nama Karyawan ke-"+(a+1)+" ");
            nmkrywn[a]=input.readLine();
        }
          
          System.out.print ("\n");
          System.out.println ("===Proses Sorting===");
          for (int a=0; a<8-1; a++) {
              System.out.print ("\n");
              System.out.println ("Iterasi "+(a+1));
              for (int b=0; b<8; b++)
                  System.out.print (nmkrywn[b]+" ");
              for (int b=a+1; b>0; b--)
              {
                  if (nmkrywn[b-1].compareTo (nmkrywn[b]) > 0)
                  {
                      System.out.println ();
                      for (int c=0; c<8; c++)
                          System.out.print(nmkrywn[c]+" ");
                      
                      String temp = nmkrywn[b];
                      nmkrywn[b]=nmkrywn[b-1];
                      nmkrywn[b-1]=temp;
                  }
                  else {
                      System.out.println();
                      for (int c=0; c<8; c++)
                          System.out.print(nmkrywn[c]+" ");
                      break;
                  }
              }
              System.out.println();
          }
          System.out.print ("\n");
          System.out.println ("===Hasil Proses Sorting/Pengurutan===");
          for (int a=0; a<8; a++)
          System.out.println(nmkrywn[a]+" ");
          System.out.println ("\n");
          
        while(jawab){
            no++;
                          
            System.out.print("\n"+no+".   Jabatan \n   1. Manager \n   2. Kabag \n   3. Pemasaran \n   4. Umum \n");
            System.out.print("   Jabatan : ");
                kodejabatan [a] = Integer.parseInt(input.readLine());
                
            System.out.print("   Status \n"+"   1. Belum Kawin \n"+"   2. Kawin \n");
            System.out.print("   Status : ");
                kodestatus[a] = Integer.parseInt(input.readLine());
                    if(kodestatus[a]==2){
                        status[a] =  "Kawin";
                        System.out.print("   Jumlah anak : ");
                            jumlahAnak[a] = Integer.parseInt(input.readLine());
                            switch(jumlahAnak [a]){
                    case 1:
                        break;
                    case 2:
                        break;
                    case 3:
                        break;
                    default: System.out.print ("   Isilah jumlah anak salah satu dari angka 1-3 \n");
                    System.out.print("   Jumlah anak : ");
                jumlahAnak [a] = Integer.parseInt(input.readLine());
                }
                    } else{
                        status[a] = "Belum Kawin";
                        jumlahAnak[a] = 0;
                    }
                    
            switch(kodejabatan[a]){
                case 1:
                    gp[a] = gajipokok[0];
                    jbtn[a] = "Manager";
                    System.out.print("   Manager \n");
                    System.out.print("   Gaji Pokok = "+gajipokok[0]+"\n");
                    tunjanganKel[a] = jumlah_tunjangan_keluarga(kodestatus[a],gp[a]);
                    tunjanganAnak[a] = jumlah_tunjangan_anak(jumlahAnak[a],gp[a]);
                    pph[a] = jumlah_pph(gp[a]);
                    gajiBersih[a] = gp[a]+tunjanganKel[a]+tunjanganAnak[a]-pph[a];
                    break;
                    
                case 2:
                    gp[a] = gajipokok[1];
                    jbtn[a] = "Kabag";
                    System.out.print("   Kabag \n");
                    System.out.print("   Gaji Pokok = "+gajipokok[1]+"\n");
                    tunjanganKel[a] = jumlah_tunjangan_keluarga(kodestatus[a],gp[a]);
                    tunjanganAnak[a] = jumlah_tunjangan_anak(jumlahAnak[a],gp[a]);
                    pph[a] = jumlah_pph(gp[a]);
                    gajiBersih[a] = gp[a]+tunjanganKel[a]+tunjanganAnak[a]-pph[a];
                    break;
                    
                case 3:
                    gp[a] = gajipokok[2];
                    jbtn[a] = "Pemasaran";
                    System.out.print("   Pemasaran \n");
                    System.out.print("   Gaji Pokok = "+gajipokok[2]+"\n");
                    tunjanganKel[a] = jumlah_tunjangan_keluarga(kodestatus[a],gp[a]);
                    tunjanganAnak[a] = jumlah_tunjangan_anak(jumlahAnak[a],gp[a]);
                    pph[a] = jumlah_pph(gp[a]);
                    gajiBersih[a] = gp[a]+tunjanganKel[a]+tunjanganAnak[a]-pph[a];
                    break;
                    
                case 4:
                    gp[a] = gajipokok[3];
                    jbtn[a] = "Umum";
                    System.out.print("   Umum \n");
                    System.out.print("   Gaji Pokok = "+gajipokok[3]+"\n");
                    tunjanganKel[a] = jumlah_tunjangan_keluarga(kodestatus[a],gp[a]);
                    tunjanganAnak[a] = jumlah_tunjangan_anak(jumlahAnak[a],gp[a]);
                    pph[a] = jumlah_pph(gp[a]);
                    gajiBersih[a] = gp[a]+tunjanganKel[a]+tunjanganAnak[a]-pph[a];
                    break;
                    
            }
            
                System.out.print("   Apakah Anda ingin mengisi data lagi ? [y/t] ");
                    tanya = input.readLine();
                        if (tanya.equalsIgnoreCase("y")){
                            a++; jawab = true;
                        }
                        else{
                        jawab = false;
                        }
        }
        
        
        int halaman=1;
        
            System.out.println("\nLaporan Gaji Karyawan Sumber Waras");
            System.out.println("Per 30 November 2020");
            System.out.println("                                                                                                                         Halaman : "+halaman);
            header();
            no = 0;
            
        for(b=0; b<=a; b++){

                no++;
            
                grantot = grantot+gp[b];
                grantot1 = grantot1+tunjanganKel[b];
                grantot2 = grantot2+tunjanganAnak[b];
                grantot3= grantot3+pph[b];
                grantot4 = grantot4+gajiBersih[b];
            
                subtot = subtot+gp[b];
                subtot1 = subtot1+tunjanganKel[b];
                subtot2 = subtot2+tunjanganAnak[b];
                subtot3 = subtot3+pph[b];
                subtot4 = subtot4+gajiBersih[b];
            
                System.out.printf ("|%-4s|%-16s|%-12s|%-16s|%-12s|%-13s|%-13s|%-17s|%-19s|\n",
                        " "+no,  " "+nmkrywn[b],  " "+jbtn[b], " "+gp[b],  " "+status[b], " "+tunjanganKel[b], " "+tunjanganAnak[b], " "+pph[b], " "+gajiBersih[b]);
            
                if(no%3==0){
                    subtotal (subtot, subtot1, subtot2, subtot3, subtot4);
                
                    System.out.println ("Tekan Tombol Enter Untuk Melanjutkan");
                    String jawab = input.readLine();
                    subtot=0; subtot1=0; subtot2=0; subtot3=0; subtot4=0;
                
                    halaman++;
                    System.out.println("                                                                                                                         Halaman : "+halaman);
                    header();
            }
        }
        
            subtotal (subtot, subtot1, subtot2, subtot3, subtot4);
        
            grandtotal (grantot, grantot1, grantot2, grantot3, grantot4);
    }
}

