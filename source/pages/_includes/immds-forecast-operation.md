source file: pages/_includes/immds-forecast.md

The operation is invoked using the POST Syntax with the Parameters payload as follows:

`POST [base]/$immds-forecast`

---

### Example

**Request the immunization forecast assessed on 2019-06-04 for a patient**

POST [base]/$immds-forecast

~~~
Accept: application/fhir+json;charset=utf-8
Content-Type: application/fhir+json;charset=utf-8
[other headers]
~~~

**Request Body**

~~~
    {
      "resourceType": "Parameters",
      "parameter": [
        {
          "name": "patient",
          "resource": {
            "resourceType": "Patient",
            "id": "forecast-example",
            "gender": "male",
            "birthDate": "2011-04-28"
          }
        },
        {
          "name" : "immunization",
          "resource" : {
            "resourceType" : "Immunization",
            "id" : "urn:uuid:12c51002-80db-485a-be81-7bfb876a8d29",
            "meta" : {
              "versionId" : "1",
              "lastUpdated" : "2019-06-05T14:40:43.967-04:00"
            },
            "contained" : [{
              "resourceType" : "Patient",
              "id" : "patient-forecast-data",
              "gender" : "male",
              "birthDate" : "2019-05-04"
            }],
            "status" : "completed",
            "vaccineCode" : {
              "coding" : [{
                "system" : "http://hl7.org/fhir/v3/VaccineType",
                "code" : "08",
                "display" : "Hep B, adolescent or pediatric"
              }]
            },
            "patient" : {
              "reference" : "Patient/forecast-example"
            },
            "recorded" : "2019-05-05T00:00:00-04:00",
            "primarySource" : false
          }
        }
      ]
    }
~~~

**Response**

~~~
HTTP/1.1 200 OK
Content-Type: application/fhir+json;charset=utf-8
[other headers]
~~~

**Response Body**

~~~
    {
      "resourceType": "Parameters",
      "parameter": [
        {
          "name": "recommendation",
          "resource": {
            "resourceType": "ImmunizationRecommendation",
            "id": "3582b411-5453-4353-93d5-c818a6b117d9",
            "meta": {
              "versionId": "1",
              "lastUpdated": "2019-06-04T14:44:10.327-04:00"
            },
            "text": {
              "status": "generated",
              "div": "<div xmlns=\"http://www.w3.org/1999/xhtml\">Forecast Results</div>"
            },
            "patient": {
              "reference": "Patient/forecast-example"
            },
            "recommendation": [
              {
                "vaccineCode": [
                  {
                    "coding": [
                      {
                        "system": "http://example.org/cdc/cvx/vaccine-code",
                        "code": "45",
                        "display": "HepB"
                      }
                    ]
                  }
                ],
                "forecastStatus": {
                  "coding": [
                    {
                      "system": "http://hl7.org/fhir/immunization-recommendation-status",
                      "code": "due",
                      "display": "due"
                    }
                  ]
                },
                "dateCriterion": [
                  {
                    "code": {
                      "coding": [
                        {
                          "system": "http://hl7.org/fhir/immunization-recommendation-date-criterion",
                          "code": "due",
                          "display": "due"
                        }
                      ]
                    },
                    "value": "2019-06-02T00:00:00-04:00"
                  },
                  {
                    "code": {
                      "coding": [
                        {
                          "system": "http://hl7.org/fhir/immunization-recommendation-date-criterion",
                          "code": "overdue",
                          "display": "overdue"
                        }
                      ]
                    },
                    "value": "2019-08-04T00:00:00-04:00"
                  },
                  {
                    "code": {
                      "coding": [
                        {
                          "system": "http://hl7.org/fhir/immunization-recommendation-date-criterion",
                          "code": "latest",
                          "display": "latest"
                        }
                      ]
                    },
                    "value": "2219-05-04T00:00:00-04:00"
                  },
                  {
                    "code": {
                      "coding": [
                        {
                          "system": "http://example.org/fhir/immunization-recommendation-date-criterion-extended",
                          "code": "valid",
                          "display": "valid"
                        }
                      ]
                    },
                    "value": "2019-06-02T00:00:00-04:00"
                  }
                ],
                "doseNumberPositiveInt": 2
              },
              {
                "vaccineCode": [
                  {
                    "coding": [
                      {
                        "system": "http://example.org/cdc/cvx/vaccine-code",
                        "code": "20",
                        "display": "DTaP"
                      }
                    ]
                  }
                ],
                "forecastStatus": {
                  "coding": [
                    {
                      "system": "http://example.org/fhir/immunization-recommendation-status",
                      "code": "duelater",
                      "display": "duelater"
                    }
                  ]
                },
                "dateCriterion": [
                  {
                    "code": {
                      "coding": [
                        {
                          "system": "http://hl7.org/fhir/immunization-recommendation-date-criterion",
                          "code": "due",
                          "display": "due"
                        }
                      ]
                    },
                    "value": "2019-07-04T00:00:00-04:00"
                  },
                  {
                    "code": {
                      "coding": [
                        {
                          "system": "http://hl7.org/fhir/immunization-recommendation-date-criterion",
                          "code": "overdue",
                          "display": "overdue"
                        }
                      ]
                    },
                    "value": "2019-08-04T00:00:00-04:00"
                  },
                  {
                    "code": {
                      "coding": [
                        {
                          "system": "http://hl7.org/fhir/immunization-recommendation-date-criterion",
                          "code": "latest",
                          "display": "latest"
                        }
                      ]
                    },
                    "value": "2169-05-04T00:00:00-04:00"
                  },
                  {
                    "code": {
                      "coding": [
                        {
                          "system": "http://example.org/fhir/immunization-recommendation-date-criterion-extended",
                          "code": "valid",
                          "display": "valid"
                        }
                      ]
                    },
                    "value": "2019-06-15T00:00:00-04:00"
                  }
                ],
                "doseNumberPositiveInt": 1
              },
              [Snipped for brevity...]
            ]
          }
        }
      ]
    }
~~~
