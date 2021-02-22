# Exceptions
Exemplo das vídeo aulas sobre Exceptions

/*Exemplo 1*/
public class Excecao {

	public static void main(String[] args) {

		try {
			int[] vetor = new int [4];

			System.out.println("Antes exception");

			vetor[4] = 1;
		}

		catch(ArrayIndexOutOfBoundsException exception) {
			System.out.println("Execeção ao acessar aum índice do vetor que não existe");
		}

		System.out.println("Esse texto será impresso após a exception");
	}

}

/*Exemplo 2*/
public class MultiplosCatch {

	public static void main(String[] args) {

		int[] numeros = {4, 8, 16, 32, 64, 128};
		int[] demon = {2, 0, 4, 8, 0};

		for(int i=0; i<numeros.length; i++) {
			try {
				System.out.println(numeros[i]+ "/" +demon[i]+ "=" +(numeros[i]/demon[i]));
			}
			catch(ArithmeticException e) {
				System.out.println("Erro ao dividir por 0");
			}
			catch(ArrayIndexOutOfBoundsException e) {
				System.out.println("Posição do array inválida");
			}
		}
	}

}

/*Exemplo 3*/
package exeptions;

public class MultiplosCatchGenerico {

	public static void main(String[] args) {

		int[] numeros = {4, 8, 16, 32, 64, 128};
		int[] demon = {2, 0, 4, 8, 0};

		for(int i=0; i<numeros.length; i++) {
			try {
				System.out.println(numeros[i]+ "/" +demon[i]+ "=" +(numeros[i]/demon[i]));
			}
			catch(ArithmeticException e) {
				System.out.println("Erro ao dividir por 0");
			}
			catch(Throwable e) {
				System.out.println("Ocorreu um erro");
			}
		}
	}

}

/*Exemplo 4*/
public class MultiplosCatchJava7 {

	public static void main(String[] args) {

		int[] numeros = {4, 8, 16, 32, 64, 128};
		int[] demon = {2, 0, 4, 8, 0};

		for(int i=0; i<numeros.length; i++) {
			try {
				System.out.println(numeros[i]+ "/" +demon[i]+ "=" +(numeros[i]/demon[i]));
			}
			catch(ArithmeticException | ArrayIndexOutOfBoundsException e) {
				System.out.println("Ocorreu um erro");
			}
		}
	}

}

/*Exemplo 5*/
public class TestandoFinally {

	public static void main(String[] args) {

		int[] numeros = {4, 8, 16, 32, 64, 128};
		int[] demon = {2, 0, 4, 8, 0};

		for(int i=0; i<numeros.length; i++) {
			try {
				System.out.println(numeros[i]+ "/" +demon[i]+ "=" +(numeros[i]/demon[i]));
			}
			catch(ArithmeticException e) {
				System.out.println("Erro ao dividir por 0");
				System.exit(0);
			}
			catch(ArrayIndexOutOfBoundsException e) {
				System.out.println("Posição do array inválida");
				System.exit(0);
			}
			finally {
				System.out.println("Essa linha é impressa sempre após o try ou catch");
				System.out.println();
			}

		}
	}
}

/*Exemplo 6*/
public class ExceptionGenerica {

	public static void main(String[] args) {

		int[] numeros = {4, 8, 16, 32, 64, 128};
		int[] demon = {2, 0, 4, 8, 0};

		for(int i=0; i<numeros.length; i++) {
			try {
				System.out.println(numeros[i]+ "/" +demon[i]+ "=" +(numeros[i]/demon[i]));
			}
			catch(Exception e) {
				System.out.println(e.getMessage());
				e.printStackTrace();
			}

		}
	}

}

/*Exemplo 7*/
public class UsandoThrows {

	public static void main(String[] args) {

		System.out.println("Digite um número decimal: ");
		try {
			double num = leNumero();
			System.out.println("Você digitou " +num);
		} 
		catch (Exception e) {
			System.out.println("Entrada inválida");
			e.printStackTrace();
		}
	}

	public static double leNumero() throws Exception{
		Scanner scan = new Scanner(System.in);
		double num = scan.nextDouble();
		return num;
	}

}
