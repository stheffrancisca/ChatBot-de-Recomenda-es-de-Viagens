# ChatBot-de-Recomenda-es-de-Viagens
ChatBot de Recomendações de Viagens.

- Você trabalha em uma agência de viagens e precisa criar um chatbot para os seus clientes. Esse chatbot deve pedir para o usuario escolher um mês de viagem. Em seguida, seu chatbot deve perguntar para qual lugar o usuário deseja viajar. Caso o local escolhido pelo usuário esteja na lista de bons lugares para viajar naquele mês, o seu chatbot deve dizer que é um ótimo lugar para viajar nesse mês. Caso o local não esteja na lista de bons locais daquele mês, seu chatbot deve:
    1. Dizer para ele quais lugares são bons para viajar nesse mês
    2. Verificar no resto dos meses se o local que o usuário quer viajar está em algum outro mês. Se tiver, seu programa deve dizer para ele qual o melhor mês para viajar para o local desejado pelo cliente.
 
       viagens_mensais = {
    "jan": ["Tailândia", "Brasil", "Antártica", "África do Sul", "Argentina"],
    "fev": ["Tailândia", "Brasil", "Argentina", "Uruguai", "África do Sul"],
    "mar": ["Brasil", "Marrocos", "EUA", "Egito", "Dubai"],
    "abr": ["Brasil", "Marrocos", "Egito", "Dubai", "Equador"],
    "mai": ["Brasil", "EUA", "Itália", "França", "Inglaterra"],
    "jun": ["Brasil", "Itália", "França", "Grécia", "Turquia"],
    "jul": ["Brasil", "Itália", "França", "Grécia", "Turquia"],
    "ago": ["Brasil", "Itália", "França", "Grécia", "Turquia"],
    "set": ["Brasil", "Croácia", "Grécia", "México", "Alemanha"],
    "out": ["Brasil", "Alemanha", "Japão", "Chile", "Indonésia"],
    "nov": ["Brasil", "México", "Costa Rica", "Barbados", "Colômbia"],
    "dez": ["Tailândia", "México", "Costa Rica", "Barbados", "Colômbia"]
}

mes_viagem = input("Qual mês deseja viajar? Digite apenas as 3 primeiras letras do mês")

lista_paises = viagens_mensais[mes_viagem]

lugar_viagem = input("Para qual lugar deseja viajar?")

if lugar_viagem in lista_paises:
    print(f"Excelente momento para viajar para {lugar_viagem}! Vamos marcar sua viagem?")
else:
    texto_lugares = ", ".join(lista_paises)
    print(f"Hmm, {mes_viagem} não é um mês muito bom para {lugar_viagem}. Recomendamos em {mes_viagem}: {texto_lugares}")
    meses_alternativos = []
    for mes in viagens_mensais:
        if lugar_viagem in viagens_mensais[mes]:
            meses_alternativos.append(mes)
    if len(meses_alternativos) > 0:
        texto_meses_alternativos = ", ".join(meses_alternativos)
        print(f"Para viajar para {lugar_viagem} recomendamos viajar em: {texto_meses_alternativos}")
