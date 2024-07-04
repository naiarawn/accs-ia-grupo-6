# Grupo 6
### Integrantes: Matheus Alves Guimarães, Pedro Henrique dos Santos, Breno Neves Falcão Soares, Lucas Longo Reboucas de Souza, João Pedro Leal Pinheiro, Naiara Barbosa Nogueira, Jean Victor
## Análise de Dados de Dengue na Bahia, Brasil

### Dashboard

Para acessar o dashboard, clique [aqui](https://app.powerbi.com/links/r_nIAcHmWH?ctid=df71f6bb-e3cc-4f5b-b532-79de261b51a2&pbi_source=linkShare&bookmarkGuid=15e78907-5663-4ad1-b124-c2d9b3c9f04c).

![Dashboard Overview](https://github.com/naiarawn/accs-ia-grupo-6/assets/115239281/62ebc31e-f95d-4d49-b68a-bbfd3967ce18)

### Descrição do Dashboard

Nosso dashboard apresenta uma análise detalhada dos casos de dengue no estado da Bahia, Brasil, abrangendo o período de 2016 a 2024. As principais visualizações incluem resumos estatísticos, rankings por cidade, mapeamento geográfico e comparações temporais. A seguir, detalhamos cada uma dessas visualizações:

#### Cards de Resumo dos Dados
Os cards de resumo fornecem uma visão geral dos principais indicadores, como o total de casos notificados, casos confirmados, óbitos, entre outros. Esses dados ajudam a identificar rapidamente o impacto da dengue na região.

![Cards de Resumo](https://github.com/naiarawn/accs-ia-grupo-6/assets/115239281/db805b17-a793-4221-80c9-13b7e974e45d)

#### Ranking de Incidência por Cidade
Esta visualização classifica as cidades da Bahia de acordo com a incidência de casos de dengue. É uma ferramenta útil para identificar áreas críticas que necessitam de intervenção imediata.

![Ranking de Incidência](https://github.com/naiarawn/accs-ia-grupo-6/assets/115239281/987283b9-7c14-4fd2-ad6f-879581c340d9)

#### Mapa da Dengue na Bahia
O mapa interativo mostra a distribuição geográfica dos casos de dengue no estado, permitindo uma análise visual rápida das áreas mais afetadas.

![Mapa da Dengue](https://github.com/naiarawn/accs-ia-grupo-6/assets/115239281/37cf5b81-5f2f-46ec-a4b7-f6a02408092e)

#### Notificações no Período (2016 - 2024)
Esta seção apresenta um gráfico temporal das notificações de dengue, permitindo observar tendências e sazonalidades ao longo dos anos.

![Notificações no Período](https://github.com/naiarawn/accs-ia-grupo-6/assets/115239281/08cfa488-5d3e-420b-a546-8294cb6005a1)

#### Comparação de Registros Positivos e Negativos de Dengue no Período
Aqui, comparamos o número de casos confirmados e descartados de dengue, oferecendo uma perspectiva sobre a precisão dos diagnósticos e a evolução da doença ao longo do tempo.

![Comparação de Registros](https://github.com/naiarawn/accs-ia-grupo-6/assets/115239281/e61f8de0-d343-4e0f-8f78-754853ddc5c2)

#### Drill Through para Informações Detalhadas
Para acessar informações mais detalhadas de cada cidade, utilize a funcionalidade de Drill Through no dashboard. Esta ferramenta permite que você explore dados específicos de cada município, fornecendo insights aprofundados sobre a situação da dengue em áreas particulares.

![Drill Through](https://github.com/naiarawn/accs-ia-grupo-6/assets/115239281/524fe614-43ce-408d-8c5c-2424fd2126f6)

Ao utilizar o Drill Through, você terá acesso às seguintes informações:

- **Total de Casos Positivos e Tempo Médio de Resolução**: Esta seção mostra o total de casos positivos de dengue em cada cidade e o tempo médio que levou para cada caso ser resolvido, seja por cura, óbito ou outro desfecho.

  ![Total de Positivo e Tempo Médio](https://github.com/naiarawn/accs-ia-grupo-6/assets/115239281/08820be6-1b33-4b86-9dee-228c12a3e731)

- **Porcentagem de Internação**: Aqui, você pode visualizar a porcentagem de casos de dengue que resultaram em internação hospitalar, ajudando a avaliar a gravidade da doença em diferentes regiões.

  ![Porcentagem de Internação](https://github.com/naiarawn/accs-ia-grupo-6/assets/115239281/86435fa6-8552-4ae1-86e5-e0375d32a340)

- **Evolução dos Casos**: Esta seção apresenta a evolução dos casos de dengue, categorizando-os como cura, sem registro, ignorado, óbito pelo agravo, óbito em investigação ou óbito por outras causas. Esta visualização ajuda a entender os desfechos dos casos ao longo do tempo.

  ![Evolução dos Casos](https://github.com/naiarawn/accs-ia-grupo-6/assets/115239281/dac5bf23-f871-44d5-8a85-4fec85c03904)

- **Sintomas Mais Comuns**: Aqui, são listados os sintomas mais frequentes relatados pelos pacientes diagnosticados com dengue, proporcionando uma visão sobre os sinais clínicos predominantes da doença.

  ![Sintomas Mais Comuns](https://github.com/naiarawn/accs-ia-grupo-6/assets/115239281/7ccbfbe3-de2c-4ce8-97e8-53304a237cf5)

#### Filtros possíveis
É possível filtrar por **Resultado do Diagnóstico**, **Cidades da Bahia**, **Período dos Registros**.

![image](https://github.com/naiarawn/accs-ia-grupo-6/assets/115239281/55d9635a-4bbd-4962-b857-6af92346b0ca)


### Conclusão
Nosso dashboard oferece uma ferramenta poderosa para monitorar e analisar a situação da dengue na Bahia. Ele é essencial para os profissionais de saúde, pesquisadores e autoridades, permitindo uma resposta mais eficaz e informada na luta contra a dengue.

# Pre-processamento de Dados de Dengue

Este repositório contém um script para o pré-processamento de dados de dengue. O objetivo deste script é limpar e preparar os dados para análises posteriores, removendo valores nulos e aplicando condições específicas de validação.

## Requisitos

- pandas
- numpy

## Instruções

1. **Leitura dos Dados**

    O script inicia lendo um arquivo CSV contendo os dados de dengue.

    ```python
    import pandas as pd
    import numpy as np

    df_leitura = pd.read_csv('dengue_sinan.csv')
    df = df_leitura
    df.info()
    ```

2. **Remoção de Valores Nulos**

    Campos obrigatórios são definidos e linhas com valores nulos nesses campos são removidas.

    ```python
    campos_obrigatorios = [
        'ID_AGRAVO', 'DT_INVEST', 'FEBRE', 'MIALGIA', 'CEFALEIA', 'EXANTEMA',
        'VOMITO', 'NAUSEA', 'DOR_COSTAS', 'CONJUNTVIT', 'ARTRITE', 'ARTRALGIA', 'PETEQUIA_N',
        'LEUCOPENIA', 'LACO', 'DOR_RETRO', 'DIABETES', 'HEMATOLOG', 'HEPATOPAT', 'RENAL',
        'HIPERTENSA', 'ACIDO_PEPT', 'AUTO_IMUNE'
    ]

    df.dropna(subset=campos_obrigatorios, inplace=True)
    ```

3. **Processamento de Campos Obrigatórios**

    Função para processar campos obrigatórios, removendo valores nulos e filtrando valores específicos.

    ```python
    def process_campos_obrigatorios(df, columns):
        for column in columns:
            if column in df.columns:
                df = df.dropna(subset=[column])
                df = df[df[column].isin([1, 2])]
        return df

    campos_obrigatorios_12 = [
        'FEBRE', 'MIALGIA', 'CEFALEIA', 'EXANTEMA',
        'VOMITO', 'NAUSEA', 'DOR_COSTAS', 'CONJUNTVIT', 'ARTRITE', 'ARTRALGIA', 'PETEQUIA_N',
        'LEUCOPENIA', 'LACO', 'DOR_RETRO', 'DIABETES', 'HEMATOLOG', 'HEPATOPAT', 'RENAL',
        'HIPERTENSA', 'ACIDO_PEPT', 'AUTO_IMUNE'
    ]

    df = df[df['FEBRE'].isin([1, 2])]
    df = process_campos_obrigatorios(df, campos_obrigatorios_12)
    df.info()
    ```

4. **Validação de Campos Específicos**

    Remoção de linhas com valores inválidos para os campos 'SOROTIPO' e 'CLASSI_FIN'.

    ```python
    df_sorotipo = df[~(((df['RESUL_VI_N'] == 1) | (df['RESUL_PCR_'] == 1)) & df['SOROTIPO'].isna())]
    df_sorotipo = df_sorotipo[~((df_sorotipo['SOROTIPO'].notna()) & (df_sorotipo['RESUL_VI_N'] != 1) & (df_sorotipo['RESUL_PCR_'] != 1))]

    df_classifin = df_sorotipo[~(df_sorotipo['DT_ENCERRA'].notna() & df_sorotipo['CLASSI_FIN'].isna())]
    df_classifin = df_classifin[~((df_classifin['CLASSI_FIN'].isin([13])) & (df_classifin['ID_AGRAVO'] == 1))]
    df_classifin = df_classifin[~((df_classifin['CLASSI_FIN'].isin([10, 11, 12])) & (df_classifin['ID_AGRAVO'] == 2))]
    ```

5. **Conversão de Datas**

    Conversão de colunas de datas para o formato datetime.

    ```python
    date_columns = ['DT_ENCERRA', 'DT_SIN_PRI', 'DT_NASC', 'DT_INVEST']
    for column in date_columns:
        df_classifin[column] = pd.to_datetime(df_classifin[column], errors='coerce')
    ```

6. **Função de Validação e Limpeza de Dados**

    Função para validar e limpar os dados de acordo com condições específicas para campos relacionados a agravos e PCR.

    ```python
    def data_pcr(df):
        df['DT_SORO'] = pd.to_datetime(df['DT_SORO'], errors='coerce')
        df['DT_NS1'] = pd.to_datetime(df['DT_NS1'], errors='coerce')
        df['DT_ALRM'] = pd.to_datetime(df['DT_ALRM'], errors='coerce')
        df['DT_VIRAL'] = pd.to_datetime(df['DT_VIRAL'], errors='coerce')
        df['DT_PCR'] = pd.to_datetime(df['DT_PCR'], errors='coerce')

        chik_condition = (df['ID_AGRAVO'] == 2)
        dengue_condition = (df['ID_AGRAVO'] == 1)
        viral_pcr_condition = (df['ID_AGRAVO'].isin([1, 2]))

        fields_conditions = [
            ('DT_PRNT', chik_condition),
            ('RES_CHIKS1', chik_condition),
            ('RES_CHIKS2', chik_condition),
            ('RESUL_PRNT', chik_condition),
            ('DT_SORO', dengue_condition & (df['DT_SORO'] >= df['DT_ALRM'])),
            ('RESUL_SORO', dengue_condition),
            ('DT_NS1', dengue_condition & (df['DT_NS1'] >= df['DT_ALRM'])),
            ('RESUL_NS1', dengue_condition),
            ('HISTOPA_N', dengue_condition),
            ('IMUNOH_N', dengue_condition),
            ('DT_VIRAL', viral_pcr_condition & (df['DT_VIRAL'] >= df['DT_ALRM'])),
            ('RESUL_VI_N', viral_pcr_condition),
            ('DT_PCR', viral_pcr_condition & (df['DT_PCR'] >= df['DT_ALRM'])),
            ('RESUL_PCR_', viral_pcr_condition)
        ]

        for field, condition in fields_conditions:
            df = df[~(condition & df[field].isna())]
            df = df[~((~condition) & df[field].notna())]

        return df

    df_pcr = data_pcr(df_classifin)
    df_pcr.describe()
    ```

7. **Salvamento dos Dados Processados**

    O dataframe final é salvo em um arquivo CSV.

    ```python
    df_pcr.to_csv('result.csv')
    ```

## Conclusão

Este script realiza um pré-processamento extensivo dos dados de dengue, garantindo que os dados estejam limpos e prontos para análises subsequentes. Ele remove valores nulos, aplica condições de validação específicas e converte colunas de datas para o formato adequado.

