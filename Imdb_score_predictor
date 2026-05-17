from json import load
import streamlit as st
import pickle
import numpy as np


def show_pred():
    def load_model():
        with open("saved_11.pkl",'rb') as file:
            d = pickle.load(file)
        return d


    st.title("How good is this movie??")
    st.write("Please answer the given questions to predict how good the movie is: ")
    

    content_rating_G=0
    content_rating_GP=0
    content_rating_M= 0
    content_rating_NC_17 = 0
    content_rating_Not_Rated= 0
    content_rating_PG= 0
    content_rating_PG_13= 0
    content_rating_Passed= 0
    content_rating_R= 0
    content_rating_TV_14= 0
    content_rating_TV_G= 0
    content_rating_TV_PG= 0
    content_rating_Unrated= 0
    content_rating_X = 0
    country_USA =0
    country_other =0


    content_all = ("G", "GP",
       "M", "NC 17", "Not Rated",
       "PG", "PG 13", "Passed",
       "R", "TV 14", "TV G",
       "TV PG", "Unrated", "X")
    
    country_list = ("USA","Other")


    duration = st.text_input("Duration", "")
    director_facebook_likes = st.text_input("Director facebook ikes", "")
    actor_1_facebook_likes = st.text_input("Main Actor facebook likes", "")
    gross = st.text_input("Gross profit", "")
    num_voted_users = st.text_input("Number of voted users", "")
    facenumber_in_poster = st.text_input("Facenumber in poster", "")
    budget = st.text_input("Budget", "")
    title_year= st.text_input("Title year", "")
    aspect_ratio = st.text_input("Aspect ratio", "")
    movie_facebook_likes= st.text_input("Movie facebook likes", "")
    Other_actor_facebbok_likes = st.text_input("Other actor facebok likes", "")
    critic_review_ratio = st.text_input("critic review ratio", "")
    country_select = st.selectbox("Country",country_list)
    if country_select=="USA":
        country_USA =1
    else:
        country_other=1

    content_all_label = st.selectbox("Content rating ",content_all)
    if content_all_label == "G":
        content_rating_G=1
    elif content_all_label == "GP":
        content_rating_GP=1
    elif content_all_label == "GP":
        content_rating_GP=1
    elif content_all_label == "M":
        content_rating_M=1
    elif content_all_label == "NC 17":
        content_rating_NC_17=1
    elif content_all_label == "Not Rated":
        content_rating_Not_Rated=1
    elif content_all_label == "PG":
        content_rating_PG=1
    elif content_all_label == "PG 13":
        content_rating_PG_13=1
    elif content_all_label == "Passed":
        content_rating_Passed=1
    elif content_all_label == "R":
        content_rating_R=1
    elif content_all_label == "TV 14":
        content_rating_TV_14=1
    elif content_all_label == "TV G":
        content_rating_TV_G=1
    elif content_all_label == "TV PG":
        content_rating_TV_PG=1
    elif content_all_label == "Unrated":
        content_rating_Unrated=1
    else:
        content_rating_X=1



    obj = [duration, director_facebook_likes, actor_1_facebook_likes,
       gross, num_voted_users, facenumber_in_poster, budget,
       title_year, aspect_ratio, movie_facebook_likes,
       Other_actor_facebbok_likes, critic_review_ratio, country_USA,
       country_other, content_rating_G, content_rating_GP,
       content_rating_M, content_rating_NC_17, content_rating_Not_Rated,
       content_rating_PG, content_rating_PG_13, content_rating_Passed,
       content_rating_R, content_rating_TV_14, content_rating_TV_G,
       content_rating_TV_PG, content_rating_Unrated, content_rating_X]

    res = 0
    oo=0
    rr = load_model()
    if st.button('predict'):
        res = rr.predict([obj])
    if res == 1:
        st.success("bad movie")
    elif res == 2:
        st.success("average movie")
    elif res == 3:
        st.success("good movie")
    else:
        st.success("excellent movie ")


def take_inp():
    duration = st.text_input("duration:", "Type Here")
show_pred()
