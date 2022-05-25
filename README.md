public class Calculator  {
    
    public Integer xvalue {get;set;}
    public Integer yvalue {get;set;}
    public Integer result {get;set;}
    public string operation {get;set;}
 
    public pagereference sub() {
        result = xvalue-yvalue;
        operation = 'Subtraction';
        return null;
    }
    
    public pagereference add() {
        result = xvalue+yvalue;
        operation = 'Addition';
        return null;
    }
    
    public pagereference mul() {
        result = xvalue*yvalue;
        operation = 'Multiplication';
        return null;
    }
    public pagereference div() {
        result = xvalue/yvalue;
        operation = 'Division';
        return null;
    }
} 

Visualstudio page
<apex:page controller="Calculator" sidebar="false">
    <apex:form >
        <apex:pageBlock title="Calculator">
          <apex:pageBlockSection columns="1" title="Arithmetic Operations">           
            <apex:pageBlockSectionItem >
                <apex:outputLabel >Enter X value :</apex:outputLabel>
                <apex:inputText value="{!xvalue}"/>                
            </apex:pageBlockSectionItem>
            <apex:pageBlockSectionItem >
                <apex:outputLabel >Enter Y value :</apex:outputLabel>
                <apex:inputText value="{!yvalue}"/>    
            </apex:pageBlockSectionItem>
             <apex:pageBlockSectionItem >
                    <apex:outputLabel > "You have performed {!operation} of {!xvalue} and {!yvalue}".
                    </apex:outputLabel>
            </apex:pageBlockSectionItem>
			<apex:outputText style="font-family: monospace; font-size: 14pt;" value="Result is : {0}">
       			<apex:param value="{!result}"/>
    		</apex:outputText>
            <apex:pageBlockSectionItem >
                <apex:commandButton value="Addition" action="{!add}"/> 
            </apex:pageBlockSectionItem>
            <apex:pageBlockSectionItem >
                <apex:commandButton value="Subtraction" action="{!sub}"/>
            </apex:pageBlockSectionItem>
            <apex:pageBlockSectionItem >
                <apex:commandButton value="Multiplication" action="{!mul}"/> 
            </apex:pageBlockSectionItem>
            <apex:pageBlockSectionItem >
                <apex:commandButton value="Division" action="{!div}"/> 
            </apex:pageBlockSectionItem>
          </apex:pageBlockSection>
       </apex:pageBlock>
    </apex:form>   
</apex:page>
