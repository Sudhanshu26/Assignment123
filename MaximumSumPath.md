import java.io.File;
import java.io.FileNotFoundException;
import java.lang.reflect.Array;
import java.util.Scanner;

public class Triangle {

	public static void main(String[] args) {

		Scanner input = new Scanner(System.in);
		System.out.println("Enter the dimension");
		int value = input.nextInt();

		int grid[][] = new int[value][value];
		String file1 = "/home/sudhanshu/Desktop/p067_triangle.txt";
		File textfile = new File(file1);
		try {
			Scanner sc = new Scanner(textfile);

			while (sc.hasNextInt()) {
				for (int i = 0; i < value; i++) {
					for (int j = 0; j <= i; j++) {
						grid[i][j] = sc.nextInt();

					}
				}

			}
			/*
			 * System.out.println(grid[0][0]); System.out.println(grid[3][3]);
			 */

			for (int i = (value - 1); i > 0; i--) {
				for (int j = i; j > 0; j--) {
					int sum1 = grid[i][j] + grid[i - 1][j - 1];
					int sum2 = grid[i][j - 1] + grid[i - 1][j - 1];
					/*
					 * System.out.println(sum1); System.out.println(sum2);
					 */
					if (sum1 > sum2) {
						grid[i - 1][j - 1] = sum1;

					} else {
						grid[i - 1][j - 1] = sum2;
					}
					System.out.println(grid[i - 1][j - 1]);
				}
			}

		}

		catch (FileNotFoundException e) {
			// TODO Auto-generated catch block
			System.out.println(file1.toString() + " : NotFound");

		}

	}

	
	}

