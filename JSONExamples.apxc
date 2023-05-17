public class JSONExamples {

    
    public static void jsonexample1(){
       StaticResource st = [Select id,name,body from StaticResource where Name=:'JSONFormat1' limit 1]; //Data is Received from System 1
        System.debug('JSON Data from System 1 = '+st.Body.toString());
        
        JSONParser parser = JSON.createParser(st.Body.toString());
        parser.nextToken(); //{
        parser.nextToken(); //"status": key
        System.debug(parser.getCurrentName());
        if(parser.getCurrentName() == 'status'){
            parser.nextToken();
            String value = parser.getText();
        System.debug('value = '+value);
        }
        parser.nextToken();
        System.debug(parser.getCurrentName());
        parser.nextToken();
        String value1 = parser.getText();
        System.debug('value1 = '+value1);
        //String value = parser.getText();
       // System.debug('value = '+value);
        //parser.nextToken();
        //System.debug(parser.getCurrentName());
        
        //Manual Parser/Generation
        //JSON
        //JSONParser
        //JSONGenerator
        //
        //Seralize & desealize
        
    }
    
    public static void jsonexample2(){
         StaticResource st = [Select id,name,body from StaticResource where Name=:'JSONFormat1' limit 1]; //Data is Received from System 1
        //System.debug('JSON Data from System 1 = '+st.Body.toString());
        
       EmployeeInfo info = (EmployeeInfo) JSON.deserialize(st.Body.toString(), EmployeeInfo.class);
        //System.debug('info = '+info.status);
         //System.debug('info = '+info.data);
        
      String jsontext =  JSON.serialize(info);
        System.debug('jsontext = '+jsontext);
    }
    
    class EmployeeInfo{
        string status{get;set;}
        List<JSONExamples.Emolpyee> data{get;set;}
    }
    
    class Emolpyee{
        string id{get;set;}
        Integer seatnumber{get;set;}
         string employee_name{get;set;}
        string employee_salary{get;set;}
        list<String> addresess;
    }
    
    public static void jsonexample3(){
       JSONGenerator generator = JSON.createGenerator(true);
        generator.writeStartObject(); //{
        
        generator.writeStringField('status', 'success');
        generator.writeNumberField('seat', 100);
        
        generator.writeFieldName('data');
        generator.writeStartArray();//[
        
        generator.writeStartObject();
        generator.writeStringField('id', '1');
        generator.writeStringField('employee_name', 'Aniket');
        generator.writeEndObject();

        generator.writeEndArray();//]
        generator.writeEndObject();//}
       String jsonstring = generator.getAsString();
        System.debug('jsonstring = '+jsonstring);
        
    }
    
    
}
