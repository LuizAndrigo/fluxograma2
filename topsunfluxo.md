```mermaid
graph TD;
    iniciar((iniciar)) --> Identificar_problema((Identificar problema)) --> Supervisor((Supervisor técnico do pós vendas)) --> Avaliar_sistema((Avaliando informações do sistema de monitoramento));
    
    Identificar_problema --> Coberto_garantia((Está coberto por garantia?));
    Coberto_garantia --> |Sim| Informar_garantia((Informa cliente sobre garantia));
    Coberto_garantia --> |Não| Informar_custos((Informa cliente sobre custos));
    
    Supervisor --> Definir_solucao((Definir tipo de solução));
    Definir_solucao --> |Online| Resolver_online((Resolução online));
    Definir_solucao --> |Visita| Programar_visita((Programar visita técnica));
    
    Resolver_online --> Encerrar((Encerra o processo));
    
    Programar_visita --> Avaliar_local((Avaliação no local));
    Avaliar_local --> |Sim| Encerrar;
    Avaliar_local --> |Não| Retirar_inversor((Retira inversor danificado e envia novo inversor Backup));
    
    Encerrar --> Retorno_estoque((Recebimento do inversor no estoque));
    Retorno_estoque --> Inversor_novo((Retornou o inversor novo?));
    
    Inversor_novo --> |Sim| Liberar_estoque((Retorna para o estoque liberado para uso));
    Inversor_novo --> |Não| Abre_garantia((Abre processo de garantia ou reparo));
    
    Abre_garantia --> Avaliacao_WEG((Solicita avaliação WEG));
    Avaliacao_WEG --> Envio_WEG((Envio do inversor para WEG));
    
    Envio_WEG --> |Troca| Troca_WEG((Troca em garantia antecipada));
    Envio_WEG --> |Avaliação| Avaliacao_WEG_fisica((Emissão de NF e envio para avaliação física));
    
    Avaliacao_WEG_fisica --> Laudo_orcamento((Emissão de laudo e/ou orçamento));
    Laudo_orcamento --> Definir_financeiro((Definir responsável financeiro));
    
    Definir_financeiro --> Retorno_WEG((Retorno do inversor da WEG));
    Retorno_WEG --> Destino_inversor((Definir destino final do inversor));
    
    Destino_inversor --> Retorno_cliente((Retorno final ao cliente));
