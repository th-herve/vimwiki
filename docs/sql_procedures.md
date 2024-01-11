# Sql procedure

Create a reusable query that can take parameter.

```sql
CREATE PROCEDURE createBouquet
    @ref_fleur int,
    @nombre int
AS
	DECLARE @fleur nvarchar(50)

    SELECT @fleur = nom_type_fleur FROM typefleur
                    WHERE ref_type_fleur = @ref_fleur;

    INSERT INTO bouquet (descriptif) VALUES (CONCAT('Assortiment de ', @fleur));

    INSERT INTO estcompose (ref_bouquet, ref_type_fleur, quantite_type_fleur) VALUES 
    (SCOPE_IDENTITY(), @ref_fleur, @nombre);
GO;
```
