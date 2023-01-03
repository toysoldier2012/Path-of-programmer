
# Concept

Multi-Version Concurrency Control, une technique résout le conflit d' écriture-lecture, distribue une timestamp à chaque [[Transaction]] comme un verrouillage dit optimiste, contrairement au verrouillage pessimiste. L’écriture et la lecture ne se bloquent pas, elle augmente la performance, résout la lecture inconsistante, la lecture non répétable, la lecture fantôme.
