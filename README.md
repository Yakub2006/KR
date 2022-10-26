# KR
        Scanner scan = new Scanner(System.in);
        int n = scan.nextInt();
        int m = scan.nextInt();
        int[][] a = new int[n][m];
        int minr = 0, maxr = n - 1, minc = 0, maxc = m - 1;
        int counter = 1;
        while (counter < m * n){
            for (int i = minc; i <= maxc; ++i){
                a[minr][i] = counter++;
            }
            minr++;
            for (int i = minr; i <= maxr; ++i){
                a[i][maxc] = counter++;
            }
            maxc--;
            for (int i = maxc; i >= minc; i--){
                a[maxr][i] = counter++;
            }
            maxr--;
            for (int i = maxr; i >= minr; i--){
                a[i][minc] = counter++;
            }
            minc++;
        }
        for (int i = 0; i < n; ++i){
            for (int j = 0; j < m; ++j){
                System.out.print(a[i][j] + " ");
            }
            System.out.println();
        }
    }
    public static void Task6(){
        Scanner scan = new Scanner(System.in);
        Random r = new Random();
        char[][] pole = new char[10][10];
        for (int i = 0; i < 10; i++){
            for (int j = 0; j < 10; j++) {
                pole[i][j] = '.';
            }
        }
        int px = r.nextInt(0, 10);
        int py = r.nextInt(0, 10);
        int d = r.nextInt(1, 5);
        while (true){
            if (d == 1 && px > 5){
                for (int i = px; i > px-5; i--){
                    pole[i][py] = 'X';
                }
                break;
            }
            if (d == 2 && px < 4){
                for (int i = px; i < px+5; i++){
                    pole[i][py] = 'X';
                }
                break;
            }
            if (d == 3 && py > 5){
                for (int i = py; i > py-5; i--){
                    pole[px][i] = 'X';
                }
                break;
            }
            if (d == 4 && py < 4){
                for (int i = py; i < py+5; i++){
                    pole[px][i] = 'X';
                }
                break;
            }
            px = r.nextInt(0, 10);
            py = r.nextInt(0, 10);
            d = r.nextInt(1, 5);
        }
        px = r.nextInt(0, 10);
        py = r.nextInt(0, 10);
        d = r.nextInt(1, 5);
        while (true){
            if (d == 1 && px > 5){
                boolean f = true;
                for (int i = px; i > px-5; i--){
                    if (pole[i][py] == 'X' || pole[i][py-1] == 'X'||pole[i][py+1] == 'X'){
                        f = false;
                        break;
                    }
                }
                if (f){
                    for (int i = px; i > px-5; i--){
                        pole[i][py] = 'X';
                    }
                    break;
                }
            }
            if (d == 2 && px < 4){
                boolean f = true;
                for (int i = px; i < px+5; i++){
                    if (pole[i][py] == 'X' || pole[i][py-1] == 'X'||pole[i][py+1] == 'X'){
                        f = false;
                        break;
                    }
                }
                if (f){
                    for (int i = px; i < px+5; i++){
                        pole[i][py] = 'X';
                    }
                    break;
                }
            }
            if (d == 3 && py > 5){
                boolean f = true;
                for (int i = py; i > py-5; i--){
                    if (pole[px-1][i] == 'X' || pole[px][i] == 'X'||pole[px+1][i] == 'X'){
                        f = false;
                        break;
                    }
                }
                for (int i = py; i > py-5; i--){
                    pole[px][i] = 'X';
                }
                break;
            }
            if (d == 4 && py < 4){
                for (int i = py; i < py+5; i++){
                    pole[px][i] = 'X';
                }
                break;
            }
            px = r.nextInt(0, 10);
            py = r.nextInt(0, 10);
            d = r.nextInt(1, 5);
        }
        for (int i = 0; i < 10; i++){
            for (int j = 0; j < 10; j++) {
                System.out.print(pole[i][j] + " ");
            }
            System.out.println();
        }
    }
 
    public static void main(String[] args) {
//        Task1(); // Done
//        Task2(); // Done
//        Task3(); // Done
//        Task4(); // Done
//        Task5(); // Done
//        Task6();
    }
}
