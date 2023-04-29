# [Memórias Static, Stack e Heap | Aprenda Rust | 04](https://youtu.be/Qezouqaoxlo)

## Memory Awereness

- Qual será o espaço de memória que o valor será armazenado quando uma variável é definida.

| Contents | | Size | Lifetime | Cleanup |
| --- | --- | --- | --- | --- |
| Static | - Program Binary<br> - Static variables<br> - String Literals<br> * known compilation size | Fixed | Whole Program | When program terminates |
| Stack | - Functions arguments<br> - Local Variables<br> - Each thread has an isolated stack<br> * know compilation size | Dynamic<br><br> *Top Limit | Function | When function returns |
| Heap | - Values that live beyond functions<br> - Shared across threads<br> - Large Values<br> - Dynamic Size Values<br> * Unknown compilation size | Dynamic<br><br> *up to computer limit | Defined by programmer or language | Manually or via GC or via RAII

## Static

- Tamanho fixo
```rust
static _Y: u32 = 13;

fn main() {
	
}
```

## Stack

- Tamanho fixo, porém o programa pode colocar e remover elementos
- Funciona como uma pilha
- Tamanho dinamico

```rust
fn main() {
	let x = 5;
	let z = true;
	let numbers = [1, 2, 3];
} // Stack frame
```

## Heap

- Não tem como prever o espaço de memória
```rust
fn main() {
	let users = get_users();
}
```

## Limpeza de memória

- RAII.
```rust
fn main() {
	let users = get_users();
} // Drop
```

## Revisão

- Area de memória que permanece durante toda a execução do programa -> Static 
- Area de memória com tamanho fixo e que não muda -> Stack
- Area de memória com tamanho dinâmico -> Heap 
