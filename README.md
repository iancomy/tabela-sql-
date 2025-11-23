# tabela-sql-
aquela table lá q eu fiz no doc soq em codigo


-- 
CREATE DATABASE redesocialtrabalhoesquecinome;
USE  redesocialtrabalhoesquecinome;


CREATE TABLE Usuario (
    id_usuario INT PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    email VARCHAR(150) NOT NULL,
    data_criacao YEAR NOT NULL
);


CREATE TABLE Post (
    id_post INT PRIMARY KEY,
    texto_postagem VARCHAR(255) NOT NULL,
    data_postagem YEAR NOT NULL,
    url_imagem VARCHAR(255),
    id_usuario INT,
    FOREIGN KEY (id_usuario) REFERENCES Usuario(id_usuario)
);


CREATE TABLE Comentario (
    id_comentario INT PRIMARY KEY,
    texto_comentario VARCHAR(255) NOT NULL,
    data_comentario YEAR NOT NULL,
    id_post INT,
    id_usuario INT,
    FOREIGN KEY (id_post) REFERENCES Post(id_post),
    FOREIGN KEY (id_usuario) REFERENCES Usuario(id_usuario)
);


INSERT INTO Usuario VALUES
(1, 'bibi', 'bibi@gmail.com', 2010),
(2, 'bibo', 'bibo@hotmail.com', 2023),
(3, 'yan', 'yan@gmail.com', 2024);


INSERT INTO Post VALUES
(1, 'eu sou bibi', 2024, NULL, 1),
(2, 'hoje eu comi bolo', 2023, 'img/bolo.png', 2),
(3, 'foto nova!', 2024, 'img/foto.png', 3);

-- ============================
-- INSERTS COMENTARIO
-- ============================
INSERT INTO Comentario VALUES
(1, 'cala a BOCA', 2024, 1, 2),
(2, 'legal!', 2024, 2, 1),
(3, 'arrasou', 2023, 3, 2);
