import streamlit as st
st.set_page_config(page_title="Plano de Aula Angola", layout="wide")
# Interface Principal
st.title("II Sistema de Planeamento Pedagógico")
st.subheader("Ensino Primário (Iniciação à 6ª Classe) - Padrão INIDI")
# 1. Painel de Identificação
with st.sidebar:
st.header("Dados da Aula")
classe = st.selectbox("Classe", ["Iniciação", "1ª Classe", "2ª Classe", "3ª Classe", "4ª Classe", "5ª Classe", "6ª Classe"])
disciplina = st.selectbox("Disciplina", ["Língua Portuguesa", "Matemática", "Estudo do Meio", "Educação Moral e Cívica", "Ed. Visual e Plástica", "Ed. Musical", "Educação Física"])
tempo = st.text_input("Tempo de Aula", "45 min")
aula_no = st.number_input("Aula Nº", min_value=1)
# 2. Estrutura do Plano
col1, col2 = st.columns(2)
with col1:
tema = st.text_input("Tema")
sumario = st.text_area("Sumário / Subtema")
obj_geral = st.text_area("Objectivos Gerais (Programa)")
with col2:
obj_aula = st.text_area("Objectivos da Aula")
conteudo = st.text_area("Conteúdo Teórico")
material = st.text_input("Material Didáctico (Ex: Giz, Pedras, Cartazes)")
# 3. Inteligência Artificial para Municípios
if st.button("I Gerar Sugestões para a Realidade Local"):
st.info("I Sugestões da IA para o contexto angolano:")
st.write("- **Material:** Usar sementes ou tampinhas para contagem; Desenhar mapas no chão do pátio com pauzinhos.")
st.write("- **Metodologia:** Elaboração conjunta baseada na vida quotidiana (ex: preços na praça local).")
st.write("- **Actividade:** Relacionar o tema com a flora/fauna da província ou provérbios locais.")
st.divider()
st.subheader("I Fases da Aula (Metodologia Activa)")
f1, f2 = st.columns(2)
with f1:
f_intro = st.text_area("1. Introdução e Motivação", placeholder="Revisão e anúncio do tema")
f_med = st.text_area("2. Mediação e Assimilação", placeholder="Explicação e diálogo")
with f2:
f_dom = st.text_area("3. Domínio e Consolidação", placeholder="Exercícios e actividades chaves")
f_cont = st.text_area("4. Controle e Avaliação", placeholder="Perguntas de verificação / TPC")
if st.button("I Gerar Plano Final"):
st.markdown(f"""
### PLANO DE AULA FORMATADO
**Classe:** {classe} | **Disciplina:** {disciplina} | **Tempo:** {tempo}
**Tema:** {tema} | **Sumário:** {sumario}
**1. Objectivos:** {obj_aula}
**2. Material:** {material}
**3. Desenvolvimento:**
* **Introdução:** {f_intro}
* **Mediação:** {f_med}
* **Consolidação:** {f_dom}
* **Avaliação:** {f_cont}
""")