## Elixir

_création d'un nouveau projet_
mix new [project_name]

_Lancer les tests_
mix test

_Un bloc logique commence par **do** et fini par **end**_

:world => symbole / atome => "variable" immuable qui vaut son nom =/= string

La dernière expression d'une fonction est la dernière valeur du bloc

On peut générer de la doc via des commentaires dans le code (**@moduledoc**/**@doc**, suivi par du markdown),
commentaires dans lesquels ont peut écrire des tests unitaires

_Lancer le CLI interractif_
iex -S mix

_Puis lancer une fonction d'un module_
iex()> MonModule.maFonction()

_Reload un module après avoir changé le code_
iex()> c "path/to/module.ex"

HTTPoison => module pour faire des requetes http

_Récupérer la version de la dépendance_
mix hex.info httpoison

Output : Yet Another HTTP client for Elixir powered by hackney                                                            Config: **{:httpoison, "~> 2.1"}**

_On récupère la dépendance  et on l'ajoute dans **mix.exs**, puis_
mix deps.get
_Pour télécharger les dépendances_

HTTPoison.get(_url_)
_retourne un tuple contenant un atom indiquant la réussite ou non de la requete
et soit le résultat de la requête soit la raison de l'échec_

Pattern matching 

`
result = HTTPoison.get(_url_)
case result do
    {:ok, data} -> data.body
    {:error, err} -> :error
    end
end
`

_Définition de fonction avec arguments par défauts_

def get(lon \\\\ 48.8566, lat \\\\ 2.3522)
