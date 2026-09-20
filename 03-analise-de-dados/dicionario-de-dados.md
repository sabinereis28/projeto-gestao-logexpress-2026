# Dicionário de Dados — LogExpress (`base-de-dados.csv`)

| Nome do Campo | Tipo de Dado | Descrição / Exemplo |
| :--- | :--- | :--- |
| `id_pedido` | Inteiro | Identificador único da entrega (Ex: 1001) |
| `data_envio` | Data (YYYY-MM-DD) | Data em que o pacote saiu do galpão |
| `data_prometida` | Data (YYYY-MM-DD) | Data limite acordada com o cliente |
| `data_entrega` | Data (YYYY-MM-DD) | Data real em que a entrega foi concluída |
| `distancia_km` | Numérico (Float) | Distância percorrida em quilômetros |
| `valor_frete` | Numérico (Float) | Valor cobrado pelo transporte em Reais (R$) |
| `status_entrega` | Texto (String) | Status final (`No Prazo`, `Atrasado`, `Cancelado`) |
| `regiao` | Texto (String) | Região de destino (`SP-Capital`, `Interior`, `Baixada`) |
