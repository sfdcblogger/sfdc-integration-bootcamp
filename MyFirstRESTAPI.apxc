@RestResource(urlMapping='/myapi')
global class MyFirstRESTAPI {
    
    @HttpGet
    global static String fetchAccount(){
        RestRequest req = RestContext.request;
        RestResponse res = RestContext.response;
        
        Map<String,Object> params = req.params;
        System.debug('params = '+params);
        
        String jsonbody =  req.requestBody.toString(); 
        System.debug('jsonbody = '+jsonbody);
        
       //url paramameter
       //URI
       //methods
       //headers
        
        List<Account> accountsList =  [select id,name,website,accountnumber from account];
        String jsonstring  = JSON.serialize(accountsList);
        return jsonstring;
    }
}
