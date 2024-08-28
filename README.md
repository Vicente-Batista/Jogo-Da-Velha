# Jogo-Da-Velha
Programa em java baseado nos estudos do 1º semestre da faculdade de SI

package AtividadesSemestre2;
import java.util.Scanner;
public class JogoDaVelhaPC {
    public static void main(String[]args){
        Scanner ler = new Scanner(System.in);

        String [][] malha = new String [3][3];

      int i = 1;
      for (int l = 0; l < malha.length; l++){
        for (int c = 0; c < malha[l].length; c++){
            malha[l][c] = i++ + "";
            System.out.print("|" + malha[l][c] + "");
        }
        System.out.println();
      }

      int jogadas = 0;
      String j1 = "x";
      String j2 = "o";

      while (jogadas < 5){
        jogadas++;

        while(jogadas==1){
            System.out.println("Escolha entre X ou O: ");
            j1 = ler.nextLine();
            boolean i1 = j1.equalsIgnoreCase("X"); 
            boolean i2 = j1.equalsIgnoreCase("O");
          
            if(i1){
              break;
              } else if(i2){
                j1 = "O";
                j2 = "X";
                break;
              } else{
                System.out.println("Esse caractere é invalido");
              }
            }
            
            System.out.println("Rodadas: " + jogadas);

            while(true){
              System.out.println("Jogador 1, escolha um campo: ");
              String campo = ler.nextLine();

              if(campo.equals(malha[0][0])){
                malha[0][0] = j1;
                break;
              } else if(campo.equals(malha[0][1])){
                malha[0][1] = j1;
                break;
              }else if(campo.equals(malha[0][2])){
                malha[0][2] = j1;
                break;
              }else if(campo.equals(malha[1][0])){
                malha[1][0] = j1;
                break;
              }else if(campo.equals(malha[1][1])){
                malha[1][1] = j1;
                break;
              }else if(campo.equals(malha[1][2])){
                malha[1][2] = j1;
                break;
              }else if(campo.equals(malha[2][0])){
                malha[2][0] = j1;
                break;
              } else if(campo.equals(malha[2][1])){
                malha[2][1] = j1;
                break;
              } else if(campo.equals(malha[2][2])){
                malha[2][2] = j1;
                break;
              } else {
                System.out.println("Essa posição esta indisponivel! ");
              }
            }
          

          for (int l = 0; l < malha.length; l++){
            for (int c = 0; c < malha[l].length; c++){
                System.out.print("|" + malha[l][c] + "");
            }
            System.out.println();
          }
          if((malha[0][0] == j1 && malha[0][1] == j1 && malha[0][2] == j1)
            || (malha[1][0] == j1 && malha[1][1] == j1 && malha [1][2] == j1)
            || (malha[2][0] == j1 && malha[2][1] == j1 && malha [2][2] == j1)
            || (malha[0][0] == j1 && malha[1][0] == j1 && malha [2][0] == j1)
            || (malha[0][1] == j1 && malha[1][1] == j1 && malha [2][1] == j1)
            || (malha[0][2] == j1 && malha[1][2] == j1 && malha [2][2] == j1)
            || (malha[0][0] == j1 && malha[1][1] == j1 && malha [2][2] == j1)
            || (malha[0][2] == j1 && malha[1][1] == j1 && malha [2][0] == j1)){

              System.out.println("O jogador 1 venceu!!");
              break;
            }
            
            if(jogadas == 5){
              System.out.println("Deu velha!!");
              break;
            }

            while(true){
              System.out.println("Jogador 2, escolha um campo: ");

                double ale = Math.random();
                int r = (int) (1 + ale * (9-1));
              String campo2 = String.valueOf(r);

              if(campo2.equals(malha[0][0])){
                malha[0][0] = j2;
                break;
              } else if(campo2.equals(malha[0][1])){
                malha[0][1] = j2;
                break;
              }else if(campo2.equals(malha[0][2])){
                malha[0][2] = j2;
                break;
              }else if(campo2.equals(malha[1][0])){
                malha[1][0] = j2;
                break;
              } else if(campo2.equals(malha[1][2])){
                malha[1][2] = j2;
                break;
              } else if(campo2.equals(malha[2][0])){
                malha[2][0] = j2;
                break;
              } else if(campo2.equals(malha[2][1])){
                malha[2][1] = j2;
                break;
              } else if(campo2.equals(malha[2][2])){
                malha[2][2] = j2;
                break;
              } else{
                System.out.println("Essa posição esta indisponivel! ");
              }
            
              
            }
            for (int l = 0; l < malha.length; l++){
              for (int c = 0; c < malha[l].length; c++){
                  System.out.print("|" + malha[l][c] + "");
              }
              System.out.println();
            }
            if((malha[0][0] == j2 && malha[0][1] == j2 && malha[0][2] == j2)
              || (malha[1][0] == j2 && malha[1][1] == j2 && malha [1][2] == j2)
              || (malha[2][0] == j2 && malha[2][1] == j2 && malha [2][2] == j2)
              || (malha[0][0] == j2 && malha[1][0] == j2 && malha [2][0] == j2)
              || (malha[0][1] == j2 && malha[1][1] == j2 && malha [2][1] == j2)
              || (malha[0][2] == j2 && malha[1][2] == j2 && malha [2][2] == j2)
              || (malha[0][0] == j2 && malha[1][1] == j2 && malha [2][2] == j2)
              || (malha[0][2] == j2 && malha[1][1] == j2 && malha [2][0] == j2)){
  
                System.out.println("O jogador 2 venceu!!");
                break;
              }
                  
      }
    }
    }

