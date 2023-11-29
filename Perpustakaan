/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */
package tugas.pbo;

import java.util.Date;
import java.util.Scanner;


public class Perpustakaan {

    /**
     * @param args the command line arguments
     */

public static void main(String[] args) {
     Scanner scanner = new Scanner(System.in);

        Buku hujan = new Buku("Hujan", "Tere Liye", "123456789");
        Buku fantastic = new Buku("Fantastic Beast", "J.K. Rowling", "398472105");
        Buku indonesiaku = new Buku("Indonesia Tercinta", "Ahmad Samsudin", "189074352");

        AnggotaPerpustakaan anggota1 = new AnggotaPerpustakaan("Ferdiansyah", "BL001", "Jl. Bumi Manti ");

        int choice;
        do {
            System.out.println("Selamat datang di Perpustakaan");
            System.out.println("Menu:");
            System.out.println("1. Anggota Perpustakaan");
            System.out.println("2. Admin");
            System.out.println("0. Keluar");

            System.out.print("Pilihan Anda: ");
            choice = scanner.nextInt();

            switch (choice) {
                case 1:
                    memberMenu(anggota1, hujan, fantastic,indonesiaku , scanner);
                    break;
                case 2:
                    adminMenu(hujan, scanner);
                    break;
                case 0:
                    System.out.println("Terima kasih telah menggunakan layanan perpustakaan.");
                    break;
                default:
                    System.out.println("Pilihan tidak valid. Silakan coba lagi.");
            }
        } while (choice != 0);

        scanner.close();
    }

    private static void memberMenu(AnggotaPerpustakaan anggota, Buku buku1, Buku buku2, Buku buku3, Scanner scanner) {
        int memberChoice;
        do {
            System.out.println("\nMenu Anggota Perpustakaan");
            System.out.println("1. Meminjam Buku");
            System.out.println("2. Mengembalikan Buku");
            System.out.println("0. Kembali ke Menu Utama");

            System.out.print("Pilihan Anda: ");
            memberChoice = scanner.nextInt();

            switch (memberChoice) {
                case 1:
                    System.out.println("Buku yang Tersedia:");
                    System.out.println("1. " + buku1.getJudulBuku());
                    System.out.println("2. " + buku2.getJudulBuku());
                    System.out.println("3. " + buku3.getJudulBuku());
                    
                    System.out.print("Pilih nomor buku yang ingin Anda pinjam: ");
                    int bookChoice = scanner.nextInt();

                    switch (bookChoice) {
                        case 1:
                            anggota.pinjamBuku(buku1, buku1.getJudulBuku(), new Date(), 7);
                            break;
                        case 2:
                            anggota.pinjamBuku(buku2, buku2.getJudulBuku(), new Date(), 7);
                            break;
                        case 3:
                            anggota.pinjamBuku(buku3, buku3.getJudulBuku(), new Date(), 7);
                            break;
                        default:
                            System.out.println("Pilihan tidak valid. Silakan coba lagi.");
                    }
                    break;
                case 2:
                    System.out.print("Masukkan judul buku yang ingin Anda kembalikan: ");
                    scanner.nextLine(); 
                    String judulKembali = scanner.nextLine();
                    anggota.kembalikanBuku(buku1, judulKembali, new Date());
                    break;
                case 0:
                    System.out.println("Kembali ke Menu Utama.");
                    break;
                default:
                    System.out.println("Pilihan tidak valid. Silakan coba lagi.");
            }
        } while (memberChoice != 0);
    }

    private static void adminMenu(Buku buku, Scanner scanner) {
        int adminChoice;
        do {
            System.out.println("\nMenu Admin");
            System.out.println("1. Menambah Koleksi Buku");
            System.out.println("0. Kembali ke Menu Utama");

            System.out.print("Pilihan Anda: ");
            adminChoice = scanner.nextInt();

            switch (adminChoice) {
                case 1:
                    Buku newBook = createBook(scanner);
                    newBook.tambahKeKoleksi();
                    break;
                case 0:
                    System.out.println("Kembali ke Menu Utama.");
                    break;
                default:
                    System.out.println("Pilihan tidak valid. Silakan coba lagi.");
            }
        } while (adminChoice != 0);
    }

    private static Buku createBook(Scanner scanner) {
        System.out.print("Masukkan judul buku : ");
        scanner.nextLine();
        String bookTitle = scanner.nextLine();

        System.out.print("Masukkan penulis buku : ");
        String bookAuthor = scanner.nextLine();

        System.out.print("Masukkan ISBN buku : ");
        String bookISBN = scanner.nextLine();

        return new Buku(bookTitle, bookAuthor, bookISBN);
    }
}
