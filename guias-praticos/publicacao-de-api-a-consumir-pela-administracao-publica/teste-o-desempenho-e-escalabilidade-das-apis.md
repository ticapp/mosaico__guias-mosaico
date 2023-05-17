# Teste o desempenho e escalabilidade das APIs

Deve ser avaliado previamente os tipos de dados, se estão abertos ou não, a quantidade de dados a extrair, o número de acessos que serão realizados e todas as características necessárias de forma a avaliar a capacidade mínima exigida.

Garanta que é possível testar a API na sua totalidade com diferentes níveis de carga para se ter uma noção real da resposta da API face ao nível de acesso. Para isso execute testes de desempenho/carga na API para determinar o tempo de resposta face a carga que pretende avaliar e identifique os limites de desempenho onde a API se começa a tornar instável. Deve monitorizar-se as APIs de forma a garantir que a mesma tem capacidade de responder à demanda, no entanto deve implementar-se mecanismos de limitação para controlo de taxa de transferência para proteção de picos inesperados.
