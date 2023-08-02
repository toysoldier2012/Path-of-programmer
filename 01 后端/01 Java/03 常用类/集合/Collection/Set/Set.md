#set

| Utilisation générale | Utilisation spécifique | Gestion des accès concurrents |
| -------------------- | ---------------------- | ----------------------------- |
| [[HashSet]]              | CopyOnWriteArraySet    | CopyOnWriteArraySet           |
| [[TreeSet]]              | EnumSet                | ConcurrentSkipListSet         |
| [[LinkedHashSet]]        |                        |                               |

# 特点

- Collection d'élément non ordonnés par défaut
- N'accepte pas doublons
