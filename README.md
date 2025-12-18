# Nome-Filmes-
Nome-Filmes-
Exercício 1 – Buscar o nome e ano dos filmes
SELECT Nome, Ano
FROM Filmes;

Exercício 2 – Buscar o nome e ano dos filmes, ordenados pelo ano (crescente)
SELECT Nome, Ano
FROM Filmes
ORDER BY Ano ASC;

Exercício 3 – Buscar pelo filme "De Volta para o Futuro", trazendo nome, ano e duração
SELECT Nome, Ano, Duracao
FROM Filmes
WHERE Nome = 'De Volta para o Futuro';

Exercício 4 – Buscar os filmes lançados em 1997
SELECT Nome, Ano
FROM Filmes
WHERE Ano = 1997;

Exercício 5 – Buscar os filmes lançados APÓS o ano 2000
SELECT Nome, Ano
FROM Filmes
WHERE Ano > 2000;

Exercício 6 – Buscar filmes com duração entre 100 e 150, ordenando pela duração
SELECT Nome, Duracao
FROM Filmes
WHERE Duracao > 100 AND Duracao < 150
ORDER BY Duracao ASC;

Exercício 7 – Quantidade de filmes lançados por ano, ordenando pela quantidade decrescente
SELECT Ano, COUNT(*) AS QuantidadeFilmes
FROM Filmes
GROUP BY Ano
ORDER BY QuantidadeFilmes DESC;

Exercício 8 – Buscar atores do gênero masculino
SELECT PrimeiroNome, UltimoNome
FROM Atores
WHERE Genero = 'Masculino';

Exercício 9 – Buscar atores do gênero feminino, ordenados pelo PrimeiroNome
SELECT PrimeiroNome, UltimoNome
FROM Atores
WHERE Genero = 'Feminino'
ORDER BY PrimeiroNome ASC;

Exercício 10 – Buscar o nome do filme e o gênero
SELECT f.Nome AS Filme, g.Nome AS Genero
FROM Filmes f
JOIN FilmesGenero fg ON f.IdFilme = fg.IdFilme
JOIN Generos g ON fg.IdGenero = g.IdGenero;

Exercício 11 – Buscar filmes do gênero "Mistério"
SELECT f.Nome AS Filme, g.Nome AS Genero
FROM Filmes f
JOIN FilmesGenero fg ON f.IdFilme = fg.IdFilme
JOIN Generos g ON fg.IdGenero = g.IdGenero
WHERE g.Nome = 'Mistério';

Exercício 12 – Buscar o nome do filme e os atores, com PrimeiroNome, UltimoNome e Papel
SELECT f.Nome AS Filme, a.PrimeiroNome, a.UltimoNome, ef.Papel
FROM Filmes f
JOIN ElencoFilme ef ON f.IdFilme = ef.IdFilme
JOIN Atores a ON ef.IdAtor = a.IdAtor;
