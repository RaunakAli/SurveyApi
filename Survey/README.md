# SurveyAPi

# CREATE TABLE "survey_db_palladium" (
    "id" serial NOT NULL PRIMARY KEY,
    "is_live" boolean NOT NULL,
    "name" varchar(100) NOT NULL,
    "description" text NOT NULL,
    "creater_id" integer NOT NULL REFERENCES "auth_user" ("id"),
    "start_date" date NOT NULL,
    "end_date" date NOT NULL,
    "survey" jsonb NOT NULL,
    "questions" jsonb
);
# CREATE TABLE "surveyresponse_db_palladium" (
    "id" serial NOT NULL PRIMARY KEY,
    "survey_id" integer NOT NULL REFERENCES "survey_db_palladium" ("id"),
    "user_id" integer NOT NULL REFERENCES "auth_user" ("id"),
    "response_timestamp" timestamp with time zone NOT NULL,
    "is_completed" boolean NOT NULL,
    "response" jsonb NOT NULL
);
