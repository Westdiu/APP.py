import time
import pandas as pd
import streamlit as st
from iqoptionapi.stable_api import IQ_Option  # pip install iqoptionapi
from ta.trend import SMAIndicator
from ta.momentum import RSIIndicator

# === CONFIGURAÇÃO DA API ===
st.set_page_config(page_title="🤖 Robô IQ Option", layout="wide")

# Dados da API (armazene em variáveis de ambiente para segurança)
EMAIL = st.sidebar.text_input("Email da IQ Option", type="default")
PASSWORD = st.sidebar.text_input("Senha da IQ Option", type="password")
SYMBOL = st.sidebar.selectbox("Ativo", ["EURUSD", "GBPUSD", "BTCUSD"])
ACCOUNT_TYPE = st.sidebar.selectbox("Conta", ["
