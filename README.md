# jokenpo sem interface
```java
package jokempo;

import java.util.Scanner;

/**
 *  *Você foi contratado como desenvolvedor júnior por uma empresa de jogos
 * educacionais. O cliente propôs um desafio simples, mas com uma pegada
 * competitiva: criar a versão digital do jogo clássico Pedra, Papel ou Tesoura,
 * onde o jogador humano irá enfrentar a &quot;inteligência artificial&quot; do
 * sistema. Seu código precisa estar claro, funcional e fácil de jogar. O
 * cliente quer um jogo leve, direto e com lógica impecável — afinal, ele quer
 * testar o raciocínio dos futuros programadores da empresa.
 *
 * @author Henrique data:03/05 - 06/05
 */
public class Jokempo {

    public static void main(String[] args) {
        //Declaração de variáveis
        int jogador, sairJogo, cV, cD, cE, maquina;
        boolean continua;
        //Scanner para o jogador poder digitar
        Scanner ler = new Scanner(System.in);
        //Entrada de dados
        cV = 0;
        cD = 0;
        cE = 0;
        /*
        Continua entra como false para quando entrar no while ela
        se tornar true para manter o loop até o jogador digitar 9
        para finalizar o loop
         */
        continua = false;

        while (!continua) {
            System.out.println("0. Pedra");
            System.out.println("1. Papel");
            System.out.println("2. Tesoura");
            System.out.println("9. Sair do jogo");
            System.out.println("Digite a opção desejada");
            jogador = ler.nextInt();

            //Escolha do jogador
            if (jogador == 0) {
                System.out.println("Jogador escolheu pedra");

            } else if (jogador == 1) {
                System.out.println("Jogador escolheu papel");

            } else if (jogador == 2) {
                System.out.println("Jogador escolheu tesoura");
                /*Quando jogador digitar 9 a variável continua
                vai ser true, porém quando entra no loop tem a
                negação na variável continua que irá entrar como
                false que finalizará o loop
                 */
            } else if (jogador == 9) {
                continua = true;
            } else {
                System.out.println("Opção invalida");
                return;
            }
            //Gerando escolha random da maquina 
            maquina = (int) (Math.random() * 3);
            //Escolha da maquina
            if (maquina == 0) {
                System.out.println("Maquina escolheu Pedra");
            } else if (maquina == 1) {
                System.out.println("Maquina escolheu Papel");
            } else if (maquina == 2) {
                System.out.println("Maquina escolheu Tesoura");
            }

            //Determinar vencedor
            if (jogador == maquina) {
                System.out.println("Empate");
                cE++;
            } else {
                if (jogador == 0 && maquina == 2 || jogador == 1 && maquina == 0 || jogador == 2 && maquina == 1) {
                    System.out.println("Você venceu");
                    cV++;
                } else {
                    System.out.println("Você perdeu");
                    cD++;
                }

            }
        }
        //Placar de pontuação
        System.out.println("Placar de pontos");
        System.out.println("Vitorias do jogador:" + cV);
        System.out.println("Vitorias da maquina:" + cD);
        System.out.println("Pontos de empate:" + cE);

    }

}
```
