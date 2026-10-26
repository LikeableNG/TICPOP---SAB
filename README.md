O código foi pensado no estilde uma pasta que estejam todas as noites de observação, claro que isso pode ser modificado facilamente para separar por ano, mas ainda é algo muito básico, ele busca dentro 
de uma pasta onde vão estar as noites de observação, depois entrea na pasta raw, nessa pasta vão estar o calib e seus objetos observados.

O processo básico para colocar o código para funcionar é, nas células de "Caminho dos Dados do Usuário" o usuário deve colocar o caminho da pasta onde estão as pastas das noites e dizer qual objeto 
deseja realizar primeiro a redução e a data escrito nos estilos dos exemplos.

Para processar as imagens corretamente leva cerca de 30 a 40 minuts no meu notebook i5 com 16GB de RAM, então dependendo do modelo e do processador será mais rápido já que e ele subdivide para 
acelerar a redução.

Ao chegar na função "Encontrar o Par e Extração da Fotometria" devesse realizar um primeiro Teste de Abertura Fotométrica, mas se não funcionar pode rodar os códigos em ordem, se perceber que a região 
que está pegadno o objeto na imagem for grande demais ou pequena demais, devesse olhar no gráfico o ponto em que começa a estabilizar e modificar o valor na célula que inicia com # Parâmetros Fotométricos:

# Parâmetros Fotométricos
raio_abertura = 7.0       # Raio da estrela (px),

alterando esse valor para o que os dados coletado sejam melhores, mas antes de rodar dnv a célula de busca, devesse lembrar de que é necessário rodar também:

# Area das aberturas para subtracao do ceu
area_aper = np.pi * (raio_abertura ** 2)
area_ann = np.pi * (r_out_sky ** 2 - r_in_sky ** 2),

pois se não rodar a abertura não mudará.

Por fim depois de ter conseguido bons dados a análise via ASTROPOP será realizada.
