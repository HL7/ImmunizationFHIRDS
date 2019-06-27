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
  "id": "parameters-in-example",
  "parameter": [
    {
      "name": "assessmentDate",
      "valueDate": "2019-06-27"
    },
    {
      "name": "patient",
      "resource": {
        "resourceType": "Patient",
        "id": "forecast-example",
        "gender": "male",
        "birthDate": "2019-04-28"
      }
    },
    {
      "name": "immunization",
      "resource": {
        "resourceType": "Immunization",
        "id": "c9d3fd2e-cf34-44f8-aa68-4413a01c4153",
        "meta": {
          "versionId": "1",
          "lastUpdated": "2019-06-27T11:55:25.382-04:00"
        },
        "contained": [
          {
            "resourceType": "Patient",
            "id": "patient-forecast-data",
            "gender": "male",
            "birthDate": "2019-04-28"
          }
        ],
        "status": "completed",
        "vaccineCode": {
          "coding": [
            {
              "system": "http://hl7.org/fhir/v3/VaccineType",
              "code": "08",
              "display": "Hep B, adolescent or pediatric"
            }
          ]
        },
        "patient": {
          "reference": "#patient-forecast-data"
        },
        "recorded": "2019-04-29T00:00:00-04:00",
        "primarySource": false
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
  "id": "parameters-out-example",
  "parameter": [
    {
      "name": "recommendation",
      "resource": {
        "resourceType": "ImmunizationRecommendation",
        "id": "69c6d273-aa68-4cd1-9a61-8b9c6506e7cc",
        "meta": {
          "versionId": "1",
          "lastUpdated": "2019-06-27T11:55:25.772-04:00"
        },
        "text": {
          "status": "generated",
          "div": "<div xmlns=\"http://www.w3.org/1999/xhtml\">Immunization Forecast Recommendation</div>"
        },
        "contained": [
          {
            "resourceType": "Patient",
            "id": "patient-forecast-data",
            "gender": "male",
            "birthDate": "2019-04-28"
          }
        ],
        "patient": {
          "reference": "#patient-forecast-data"
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
                "value": "2019-05-27T00:00:00-04:00"
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
                "value": "2019-07-28T00:00:00-04:00"
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
                "value": "2219-04-28T00:00:00-04:00"
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
                "value": "2019-05-27T00:00:00-04:00"
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
                "value": "2019-06-28T00:00:00-04:00"
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
                "value": "2019-07-28T00:00:00-04:00"
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
                "value": "2169-04-28T00:00:00-04:00"
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
                "value": "2019-06-09T00:00:00-04:00"
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
