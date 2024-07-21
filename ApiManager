package org.example;

import com.fasterxml.jackson.databind.ObjectMapper;
import com.mashape.unirest.http.HttpResponse;
import com.mashape.unirest.http.Unirest;
import com.mashape.unirest.http.exceptions.UnirestException;
import com.mashape.unirest.request.GetRequest;

public class ApiManager {


    public String getJokeByApi(String category) {
        try {
            GetRequest getRequest = Unirest.get("https://v2.jokeapi.dev/joke/" + category + "?format=txt");
            //ביקשנו בקשת API
            HttpResponse<String> response = getRequest.asString();
            return response.getBody();
        } catch (UnirestException e) {
            throw new RuntimeException(e);
        }
    }

    public String getMathApi(String category) {
        try {
            GetRequest getRequest = Unirest.get("http://numbersapi.com/random/" + category);
            HttpResponse<String> response = getRequest.asString();
            return response.getBody();
        } catch (UnirestException e) {
            throw new RuntimeException(e);
        }
    }

    public String getFactApi() {
        try {
            GetRequest getRequest = Unirest.get("https://catfact.ninja/fact");
            HttpResponse<String> response = getRequest.asString();
            String json = response.getBody();
            ObjectMapper objectMapper = new ObjectMapper();
            CatFact catFact2 = objectMapper.readValue(json, CatFact.class);
            return catFact2.getFact();
        } catch (Exception e) {
            throw new RuntimeException(e);
        }
    }


}
