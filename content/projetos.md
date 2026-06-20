---
title: "Sistema de Atendimento Bancário em Python"
date: "2026-05-24"
---
# Sistema de Atendimento Bancário em Python

# Objetivo

Desenvolver um sistema de simulação de atendimento bancário utilizando filas para gerenciar clientes comuns e preferenciais.

## Descrição

O projeto foi implementado em Python com o objetivo de simular o funcionamento de uma fila de atendimento bancário. O sistema permite gerar senhas, registrar clientes comuns e preferenciais, controlar o tempo de espera, realizar atendimentos e calcular estatísticas de funcionamento.

## Funcionalidades

* Geração de senhas para clientes comuns e preferenciais.
* Controle de fila de espera.
* Priorização de clientes preferenciais.
* Atualização do tempo de espera.
* Remoção automática de clientes desistentes.
* Cálculo de estatísticas de atendimento.

## Conceitos Utilizados

* Estruturas de dados (listas).
* Estruturas de repetição.
* Estruturas condicionais.
* Manipulação de filas.
* Algoritmos de priorização.

## Tecnologias

* Python

## Competências Demonstradas

* Programação estruturada.
* Resolução de problemas.
* Desenvolvimento de algoritmos.
* Simulação de processos reais.

## Código-Fonte

````yml
fila = []
dados = ""
senha = 0
total_atendidos = 0
desistentes = 0
soma = 0
while True:
    print("Menu")
    print("G - Gerar senha comum")
    print("P - Gerar senha preferencial")
    print("C - Chamar próximo cliente")
    print("A - Avançar tempo")
    print("F - Exibir fila")
    print("E - Exibir estatísticas")
    print("S - Sair")
    dados = input("Escolha uma opção: ").upper()
    # Condições
    if dados == "G":
        senha += 1
        cliente = [senha, 'C', 0]
        fila.append(cliente)
        print(f'Senha {senha} gerada para cliente comum.')

    elif dados == "P":
        senha += 1
        cliente = [senha, 'P', 0]
        fila.append(cliente)
        print(f'Senha {senha} gerada para cliente preferencial.')

    elif dados == "C":
        if len(fila) == 0:
            print('Não há clientes aguardando.')
        else:
            # 1. Descobrir o maior tempo manualmente
            maior_tempo = fila[0][2]
            for cliente in fila:
                if cliente[2] > maior_tempo:
                    maior_tempo = cliente[2]
            cliente_chamado = None
            # 2. Procurar preferencial com maior tempo
            for cliente in fila:
                if cliente[2] == maior_tempo and cliente[1] == 'P':
                    cliente_chamado = cliente
                    break
            # 3. Se não tiver preferencial, pega qualquer com maior tempo
            if cliente_chamado == None:
                for cliente in fila:
                    if cliente[2] == maior_tempo:
                        cliente_chamado = cliente
                        break
            # 4. Chamar cliente
            print('Cliente chamado:')
            print(f'Senha {cliente_chamado[0]} | Tipo {cliente_chamado[1]} | Espera {cliente_chamado[2]}')
            fila.remove(cliente_chamado)
            total_atendidos += 1
            soma += cliente_chamado[2]
    elif dados == "A":
        i = 0
        while i < len(fila):
            fila[i][2] += 1
            if fila[i][2] >= 10:
                print('Cliente desistiu:')
                print(f'Senha {fila[i][0]} | Tipo {fila[i][1]} | Espera {fila[i][2]}')
                fila.pop(i)
                desistentes += 1
            else:
                i += 1

    elif dados == "F":
        print("Fila atual:")
        if len(fila) == 0:
            print("Fila vazia")
        else:
            for cliente in fila:
                print(f'Senha {cliente[0]} | Tipo {cliente[1]} | Espera {cliente[2]}')

    elif dados == "E":
        print('Estatísticas:')
        print(f'Total de senhas geradas: {senha}')
        print(f'Total de clientes atendidos: {total_atendidos}')
        print(f'Total de clientes que desistiram: {desistentes}')
        print(f'Total de clientes aguardando na fila: {len(fila)}')
        if total_atendidos > 0:
            media = soma/total_atendidos
            print(f'Tempo médio de espera dos clientes: {media:.2f}')
        else:
            print('Não é possível calcular o tempo médio de espera.')
    
    elif dados == "S":
        print('Encerrando sistema...')
        break
    
    else:
        print('Opção inválida!')
````

[https://github.com/SGVick7/Sistema-de-Atendimento-Bancario.git](LINK_DO_REPOSITORIO)


---
date: 2026-06-05
----------------

# Análise da Representação Gráfica de Dados sobre Homicídios no Brasil

## Objetivo

Avaliar criticamente a representação gráfica utilizada em uma notícia sobre a evolução dos homicídios no Brasil e discutir como escolhas visuais podem influenciar a interpretação dos dados.

## Descrição

Neste trabalho foi realizada uma análise da representação gráfica utilizada em uma reportagem sobre a redução dos homicídios no Brasil. O estudo investigou como o uso de um eixo vertical truncado pode gerar uma percepção exagerada da magnitude da redução observada.

Para isso, foram construídos dois gráficos:

1. Reprodução da representação com eixo Y truncado.
2. Representação alternativa com eixo iniciando em zero.

A comparação permitiu demonstrar como a escolha da escala interfere na interpretação visual dos dados.

## Técnicas Aplicadas

* Estatística descritiva.
* Visualização de dados.
* Comunicação estatística.
* Análise crítica de gráficos.

## Ferramentas Utilizadas

* R
* ggplot2
* R Markdown
* RPubs

## Principais Conclusões

* Os dados confirmam a redução dos homicídios.
* O gráfico original amplifica visualmente a magnitude da queda.
* A interpretação de gráficos deve considerar escalas e eixos utilizados.

## Habilidades Demonstradas

* Construção de gráficos com ggplot2.
* Comunicação de resultados estatísticos.
* Pensamento crítico em visualização de dados.
* Produção de relatórios reprodutíveis em R Markdown.

## Relatório Completo

[http://rpubs.com/sgvick/1439116](LINK_DO_RPUBS)

## Fonte dos Dados

Dados de homicídios no Brasil (2010–2023) utilizados para fins educacionais e de análise gráfica.