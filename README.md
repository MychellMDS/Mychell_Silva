# Mychell_Silva
Meu repositorio de engenharia de software

Sistema para clinica veterinaria...
Autor: Mychell Marques da silva

---
# 1.Descrição do sistema

Sistema para clinica veterinaria...

Nome da clínica: Nossas patas

=======


1.Uma clínica veterinária atende apenas os animais: gatos e cachorros.                        
2.Os clientes devem fazer um cadastro de si e dos animais.                                    
3.Os clientes devem informar as condições nas quais os animais chegam.                        
4.Os clientes devem informar o tipo de ração que o animal come.                               
5.O cliente deve informar hábitos do animal.                                                  
6.Para cada animal é possível que mais de um veterinário o atenda.                            
7.Os animais podem chegar e serem atendidos de acordo com uma agenda do dia.                  
8.Cada animal atendido receberá uma ficha e um prontuário.                                    
9.Outros donos podem querer marcar horários de atendimento futuro.                            
10.O atendimento gera uma receita para o animal.                                              
11.Quando um cliente chega na clínica veterinária ele é atendido por um atendente.            
12.O atendente deve verificar se existe agenda disponível com um veterinário.                 
13.O atendente deve colocar o cliente e seu animal na fila de espera, se for o caso.    
14.O atendente deve levar o cliente e o animal até o veterinário.   
15.O veterinário deve realizar uma entrevista com o dono do animal.     
16.O resultado da entrevista deve ir para um formulário.    
17.O veterinário deverá examinar o animal e anotar em prontuário(ficha) suas observações.   
18.Dependendo da situação do animal este receberá uma receita.  
19.Dependendo da gravidade da situação o animal será atendido primeiro.                       
20.Caso um cliente desmarque a consulta o próximo poderá ser antecipado.        
21.Caso o cliente não apareça ele poderá remarcar.  
22.Os clientes poderão pagar parcelado a consulta.  
23.A clinica vende plano de saúde pra PETS. 
24.Cliente terá desconto caso seja sua primeira consulta.   
25.Cliente receberá brindes se for sua 5º consulta. 



---
# 2. Diagrama do banco de dados
```mermaid
erDiagram
    CLIENTE {
        int id_cliente PK
        string nome
        string telefone
        string endereco
        boolean primeira_consulta
        int numero_consultas
    }

    ANIMAL {
        int id_animal PK
        string nome
        string tipo
        string raca
        string condicao
        string habitos
        string tipo_racao
        int id_cliente FK
    }

    VETERINARIO {
        int id_veterinario PK
        string nome
        string especialidade
    }

    ATENDIMENTO {
        int id_atendimento PK
        date data
        time hora
        string observacoes
        string receita
        int id_animal FK
        int id_veterinario FK
    }

    AGENDA {
        int id_agenda PK
        date data
        time hora
        int id_veterinario FK
        int id_cliente FK
        int id_animal FK
    }

    PLANO_SAUDE {
        int id_plano PK
        string descricao
        decimal valor
        int id_cliente FK
    }

    CLIENTE ||--o{ ANIMAL : "possui"
    CLIENTE ||--o{ PLANO_SAUDE : "adquire"
    ANIMAL ||--o{ ATENDIMENTO : "recebe"
    VETERINARIO ||--o{ ATENDIMENTO : "realiza"
    VETERINARIO ||--o{ AGENDA : "tem"
    CLIENTE ||--o{ AGENDA : "marca"
    ANIMAL ||--o{ AGENDA : "tem"



```
![]()

---
# 3. Diagrama de casos de uso 

![https://github.com/MychellMDS/Mychell_Silva/blob/main/trabalho.drawio.png](https://github.com/MychellMDS/Mychell_Silva/blob/main/trabalho.drawio.png)
---
# 4. Principais telas de uso sistema

![https://github.com/MychellMDS/Mychell_Silva/blob/main/Captura%20de%20tela%202024-08-15%20230238.png?raw=true](https://github.com/MychellMDS/Mychell_Silva/blob/main/Captura%20de%20tela%202024-08-15%20230238.png?raw=true)
![https://github.com/MychellMDS/Mychell_Silva/blob/main/foto2024-08-15%20230146.png?raw=true](https://github.com/MychellMDS/Mychell_Silva/blob/main/foto2024-08-15%20230146.png?raw=true)
![https://github.com/MychellMDS/Mychell_Silva/blob/main/Captura%20de%20tela%202024-08-15%20230828.png?raw=true](https://github.com/MychellMDS/Mychell_Silva/blob/main/Captura%20de%20tela%202024-08-15%20230828.png?raw=true)
---
# 5. Arquetutura do sistema

![https://github.com/MychellMDS/Mychell_Silva/blob/main/Captura%20de%20tela%202024-08-15%20175152.png?raw=true](https://github.com/MychellMDS/Mychell_Silva/blob/main/Captura%20de%20tela%202024-08-15%20175152.png?raw=true)

