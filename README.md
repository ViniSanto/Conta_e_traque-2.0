# Conta e Traque 2.0

Jogo educativo de matemática em primeira pessoa, feito na **Unreal Engine 5.6**. Durante a partida aparecem contas em painéis na arena e o jogador escolhe e confirma a resposta certa entre as opções, enquanto enfrenta robôs com o seu blaster.

Projeto desenvolvido na **UTFPR**.

## Requisitos

- Unreal Engine **5.6**
- Plugin **Modeling Tools Editor Mode** (já vem habilitado no `.uproject`)
- Git (o repositório guarda os assets binários `.uasset` e `.umap`)

O projeto é feito **só com Blueprints**, então não precisa de Visual Studio nem de compilar código C++.

## Como abrir

1. Clone o repositório:
   ```bash
   git clone https://github.com/ViniSanto/Conta_e_traque-2.0.git
   ```
2. Abra o `Conta_e_traque.uproject` com a Unreal Engine 5.6.
3. O mapa padrão é `Mapas/Arena`. Aperte **Play** para testar.

## Controles

| Ação | Input Action |
|---|---|
| Andar | `IA_move` |
| Olhar | `IA_look` |
| Pular | `IA_jump` |
| Atirar | `IA_tiro` |
| Escolher uma resposta | `IA_select` |
| Confirmar a escolha | `IA_confirmar` |

As teclas ficam no Input Mapping Context `Input/IMC_default`.

## Estrutura do projeto

```
Content/
├── Blueprints/      GM_base (Game Mode), CBP_player (personagem), ABP_tiro (projétil)
├── Input/           IMC_default e as Input Actions (IA_*)
├── Mapas/           Arena (mapa principal)
├── MaterialContas/  Materiais das contas e respostas (M_equacoes, M_contaR_*, MPC_*, contorno)
├── TexturaContas/   Texturas das contas (Text0–Text5)
├── Models/          Meshes e materiais dos painéis, do contorno e do tiro
└── Personagens/     Herói em primeira pessoa (heroi_fp, ABP_heroi), robô inimigo (robo1) e logo da UTFPR
```

### Peças principais

- **`GM_base`**: Game Mode padrão do projeto.
- **`CBP_player`**: personagem do jogador. A câmera tem como filho o mesh `BracosFP` (braços e arma do herói em primeira pessoa), animado pelo Animation Blueprint do herói.
- **`ABP_tiro`**: o Actor do projétil disparado pelo jogador.
- **`MPC_equacoes` / `MPC_respostas`**: Material Parameter Collections que controlam qual conta e quais respostas aparecem nos painéis.
- **`Material_Contorno`**: o contorno que destaca a resposta selecionada.
- **`robo1`**: o robô inimigo, com animações de parado e correndo.

## Arte

Os modelos e texturas usam estilo pixelado: as texturas são importadas com filtro **Nearest** e sem mipmaps. Os materiais dos personagens usam Roughness 1 e Metallic 0. Ao importar uma textura nova, use as mesmas configurações para manter o visual.

## Equipe

- [ViniSanto](https://github.com/ViniSanto)
- jeconiasrg

## Licença

Ainda não definida.
