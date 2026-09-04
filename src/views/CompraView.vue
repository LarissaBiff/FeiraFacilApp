<script setup>
import { ref } from 'vue';

const pedidos = ref([
  {
    codigo: 'PED-001',
    cliente: 'Maria da Silva',
    itens: [
      {
        id: 1,
        produto: 'Tomate',
        precoUnitario: 8.5,
        quantidade: 2,
      },
      {
        id: 2,
        produto: 'Batata',
        precoUnitario: 6,
        quantidade: 3,
      },
    ],
  },
  {
    codigo: 'PED-002',
    cliente: 'João Pereira',
    itens: [
      {
        id: 3,
        produto: 'Banana',
        precoUnitario: 7.5,
        quantidade: 2,
      },
      {
        id: 4,
        produto: 'Maçã',
        precoUnitario: 12,
        quantidade: 1,
      },
      {
        id: 5,
        produto: 'Laranja',
        precoUnitario: 5.5,
        quantidade: 4,
      },
    ],
  },
])


</script>

<template>
  <main class="container page">
    <header class="page-header">
      <h1>Fazer compra</h1>
      <p>
        Cadastre o cliente e adicione os produtos do pedido.
      </p>
    </header>

    <section class="card" aria-labelledby="dados-pedido">
      <h2 id="dados-pedido">Dados do pedido</h2>

      <div class="form-grid form-grid-two-columns">
        <div class="form-group">
          <label for="codigoPedido">
            Código do pedido
          </label>

          <input
            v-model="pedidos"
            id="codigoPedido"
            name="codigoPedido"
            type="text"
            placeholder="Ex.: PED-001"
          />
        </div>

        <div class="form-group">
          <label for="nomeCliente">
            Nome do cliente
          </label>

          <input
            v-model="pedidos"
            id="nomeCliente"
            name="nomeCliente"
            type="text"
            placeholder="Digite o nome do cliente"
          />
        </div>
      </div>

      <!-- O aluno deverá implementar as mensagens de validação. -->

      <!-- Exiba aqui uma mensagem quando os dados forem inválidos. -->
    </section>

    <section class="card" aria-labelledby="adicionar-produto">
      <h2 id="adicionar-produto">Adicionar produto</h2>

      <div class="form-grid form-grid-product">

        <div class="form-group">
          <label for="nomeProduto">
            Produto
          </label>

          <input
            v-model="pedido"
            id="nomeProduto"
            name="nomeProduto"
            type="text"
            placeholder="Ex.: Tomate"
          />
        </div>

        <div class="form-group">
          <label for="precoUnitario">
            Preço unitário
          </label>

          <input
            v-model="pedido"
            id="precoUnitario"
            name="precoUnitario"
            type="number"
            min="0"
            step="0.01"
            placeholder="0,00"
          />
        </div>

        <div class="form-group">
          <label for="quantidade">
            Quantidade
          </label>

          <input
            v-model="pedido"
            id="quantidade"
            name="quantidade"
            type="number"
            min="1"
            step="1"
            placeholder="0"
          />
        </div>
      </div>

      <div class="form-actions">
        <button 
        class="button button-primary" 
        type="button"
        @click="pedido"
        >
          Adicionar produto
        </button>
      </div>
    </section>

    <section class="card" aria-labelledby="itens-pedido">
      <h2 id="itens-pedido">Itens do pedido</h2>

      <!--
        O aluno deverá utilizar uma diretiva condicional para
        mostrar uma mensagem na tela quando não houver produtos.
      -->

      <!-- Exiba aqui uma mensagem quando nenhum produto foi adicionado ao pedido.-->

      <!--
        O aluno deverá utilizar v-for para apresentar os produtos.
      -->
      <div class="table-responsive" >
        <table>
          <thead>
            <tr>
              <th scope="col">Produto</th>
              <th scope="col">Preço unitário</th>
              <th scope="col">Quantidade</th>
              <th scope="col">Total</th>
              <th scope="col">Ação</th>
            </tr>
          </thead>

          <tbody>
              <tr v-for="pedido in pedidos">
                <td>{{pedido}}</td>
                <td>{{  }}</td>
                <td>{{  }}</td>
                <td>{{  }}</td>
                <td>
                  <button type="button">Excluir</button>
                </td>
              </tr>
          </tbody>

        </table>
      </div>

      <div class="order-total">
        <span>Total da compra</span>

        <!-- O aluno deverá apresentar aqui o total calculado. -->
        <strong>R$ 0,00</strong>
      </div>

      <div class="form-actions">
        <button class="button button-secondary" type="button">
          Limpar
        </button>

        <button class="button button-primary" type="button">
          Finalizar pedido
        </button>
      </div>
    </section>
  </main>
</template>


