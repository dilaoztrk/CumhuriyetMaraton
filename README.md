public class Main {
    public static void main(String[] args) {

        String[] ogrenci = {"Kadir", "Gökhan", "Hakan", "Suzan", "Pınar", "Mehmet", "Ali", "Emel", "Fırat", "James", "Jale", "Ersin", "Deniz", "Gözde", "Anıl", "Burak"};
        int[] dakika = {341, 273, 278, 329, 445, 402, 388, 270, 243, 334, 412, 393, 299, 343, 317, 265};

        System.out.println("İlk üç dereceyi alan öğrenciler:");
        ilk3(ogrenci, dakika);


        int[] classCounts = sınıfSıralama(dakika);
        System.out.println("\n A-> " + classCounts[0] + " öğrenci");
        System.out.println("B-> " + classCounts[1] + " öğrenci");
        System.out.println("C-> " + classCounts[2] + " öğrenci");
    }

    public static void ilk3(String[] isim, int[] derece) {
        zamanSıralama(isim, derece);

        for (int i = 0; i < 3; i++) {
            System.out.println(isim[i] + ": " + derece[i]);
        }
    }

    public static int[] sınıfSıralama(int[] derece) {
        int[] sınıfBulma = new int[3];

        for (int dakika : derece) {
            if (dakika >= 200 && dakika < 300) {
                sınıfBulma[0]++;
            } else if (dakika >= 300 && dakika < 400) {
                sınıfBulma[1]++;
            } else {
                sınıfBulma[2]++;
            }
        }

        return sınıfBulma;
    }

    public static void zamanSıralama(String[] isim, int[] derece) {
        for (int i = 0; i < derece.length - 1; i++) {
            for (int j = 0; j < derece.length - i - 1; j++) {
                if (derece[j] > derece[j + 1]) {
                    int tempDerece = derece[j];
                    derece[j] = derece[j + 1];
                    derece[j + 1] = tempDerece;

                    String tempİsim = isim[j];
                    isim[j] = isim[j + 1];
                    isim[j + 1] = tempİsim;
                }
            }
        }
    }
}
