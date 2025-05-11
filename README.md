# 🏭 Data Warehouse & Cockpits – Exportações do Brasil (2000–2023)

## Modelagem do Data Warehouse

### Tabela Fato f_exportacao

id_exportacao

data_exportacao

valor_fob

quantidade

id_produto

id_estado_origem

id_pais_destino

id_porto_origem

id_transporte

### Dimensões

dim_tempo (dia, mês, trimestre, ano)

dim_produto (código NCM, descrição, categoria)

dim_estado (UF, nome, região)

dim_pais (código, nome)

dim_porto (código, nome, estado)

dim_transporte (modal: rodoviário, ferroviário, marítimo, aéreo, dutoviário)

## Fluxo ETL & Transformações

Extração: leitura de /data/exportacoes_2000_2023.csv para staging.

Limpeza: remoção de valores inválidos e padronização de campos.

Enriquecimento: lookup de descrições e categorização adicional.

Carga: scripts SQL (stage_to_dw.sql) para inserção incremental no DW.

Validação: contagem de registros e comparação com totais oficiais.

## Cockpits & Dashboards (Power BI)

Visão Geral: evolução anual das exportações (FOB).

Top 10 Produtos: ranking por valor e quantidade.

Estados Exportadores: barras por UF.

Portos Principais: mapa e ranking dos 5 maiores fluxos.

Destinos: bolhas de valor exportado por país.

Modalidades de Transporte: participação de cada modal.

Mapa Coroplético: exportações por região.
