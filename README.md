# Exercicio095.py

time = list()
jogador = dict()
partidas = list()
while True:
    jogador.clear()
    jogador['nome'] = str(input('NOME DO JOGADOR:'))
    tot = int(input(f'Quantas partidas {jogador["nome"]} jogou?'))
    partidas.clear()
    for c in range(0, tot):
        partidas.append(int(input(f'Quantos gols na partida {c + 1}? ')))
    jogador['gols'] = partidas[:]
    jogador['total'] = sum(partidas)
    time.append(jogador.copy())
    while True:
        resp = str(input('Quer continuar? [S/N]')).upper()[0]
        if resp in 'SN':
            break
        print('ERRO, Favor digitar apenas S ou N!')
    if resp == 'N':
        break
print('=-'*30)
print('Cod ', end='')
for i in jogador.keys():
    print(f'{i:<15}', end='')
print()
print('=-'*30)
for k, v in enumerate(time):
    print(f'{k:>3}', end='')
    for d in v.values():
        print(f'{str(d):<15}', end='')
    print()
print('=-'*30)
while True:
    busca = int(input('Mostra dados de qual jogador? (999 para parar)'))
    if busca == 999:
        break
    if busca >= len(time):
        print(f'ERRO! Não existe jogador com o codgo: {busca}')
    else:
        print(f' -- LEVANTAMENDO DO JOGADOR -- {time[busca]["nome"]}:')
        for i, g in enumerate(time[busca]['gols']):
            print(f'   No jogo {i+1} fez {g} gols.')
        print('=-'*30)
print('VOLTE SEMPRE!')
