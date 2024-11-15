# Criadores do Projeto

- Beatriz Cristina emerenciano RA : 22.222.041-0
- João Guilherme Rogante RA : 22.223.081-5

# Fechadura Eletrônica em Assembly 

Este projeto envolve a criação de uma interface que integra um teclado matricial, um display LCD e um motor que simula o funcionamento de uma fechadura. 
Tudo é controlado por um microcontrolador programado na linguagem Assembly, proporcionando um sistema de acesso seguro por senha.

# Implementação de Sistema de Senha em Assembly
O propósito central deste projeto é desenvolver um sistema de entrada de senha em um microcontrolador 8051 programado em Assembly. 
Utilizando um teclado matricial para inserção do PIN e um display LCD para exibir mensagens conforme a senha digitada, o projeto busca aprofundar o entendimento da arquitetura de computadores e da programação em Assembly.

# Funcionalidades

- Entrada de Senha via Teclado Matricial: O usuário pode inserir uma senha utilizando um teclado matricial 4x4 conectado ao microcontrolador.

- Exibição Dinâmica no Display LCD: Mensagens e instruções são apresentadas em um display LCD conforme as interações do usuário. O sistema utiliza tabelas de consulta (LUTs) para facilitar a gestão e exibição dos textos.

- Verificação e Autenticação da Senha: O microcontrolador verifica se a senha digitada corresponde à senha armazenada, validando o acesso.

- Feedback Visual ao Usuário: O display LCD fornece feedback imediato, indicando se o acesso foi autorizado ou negado, melhorando a experiência do usuário.

- Opção de Alteração de Senha: Após uma autenticação bem-sucedida, o usuário tem a opção de pressionar o botão "#" para modificar a senha de acesso do sistema.

# Perifericos  

- Microcontrolador 8051
- Teclado Matricial 4x4
- Display LCD
- Motor

**Para simular todos os perifericos do projeto, foi utilizado o emulador Edsim51.**

# Execução do Projeto

**Fluxograma:** 

![image](https://github.com/user-attachments/assets/84bed68e-d983-479b-9692-22234bc4b423)



**Frequência Recomendada para Testes:**

- Utilize uma frequência de 100 Hz para a exibição inicial das mensagens.
- Antes de inserir dados no teclado, ajuste a frequência para 10 Hz.
- Frequências mais altas podem causar problemas de múltiplas entradas no teclado matricial.

  

 **Processo Quando o PIN é Solicitado:** 

- A função principal (Main) é iniciada.
- Chama-se a função ExibirDisplay para mostrar a mensagem "DIGITE:" no LCD.
- O loop Novamente percorre os caracteres da mensagem para apresentá-los na tela.
- A função ScanTeclado entra em ação para aguardar a entrada do PIN pelo usuário.
- Após a digitação do PIN, o programa utiliza a função VerificarEntrada para conferir se a senha está correta.
- Se o PIN for válido, a função Concedido exibe "COFRE ABERTO".
- Se o PIN for inválido, a função Negado exibe "COFRE FECHADO".

**Quando o PIN Correto é Inserido:**

- A cada tecla pressionada, a função VerificarEntrada confirma se o dígito corresponde ao esperado.
-Se todos os dígitos estiverem corretos, a função Concedido é acionada para permitir o acesso.
- O programa ativa o pino de controle do motor (P3.0), fazendo-o girar no sentido anti-horário.
- Um temporizador é iniciado para controlar o tempo necessário para meia volta do motor.
- Ao final do temporizador, o programa desativa o pino P3.0, interrompendo o movimento do motor.

**Quando o PIN Incorreto é Inserido:**

- A função VerificarEntrada verifica cada tecla pressionada em busca de inconsistências.
- Se algum dígito não corresponder, a função Negado é chamada para negar o acesso e informar o usuário.

# Telas

**Cofre Aberto**
![image](https://github.com/user-attachments/assets/8e975278-0e97-4923-b0c8-b76ddf6ac269)

**Cofre Fechado**
![image](https://github.com/user-attachments/assets/1eebd604-c2ef-4a47-8aa6-6ff1d05874e3)

# Fontes de Referência
- https://web.mit.edu/6.115/www/document/8051.pdf
- https://www.youtube.com/@canalwrkits
- https://edsim51.com/examples/











