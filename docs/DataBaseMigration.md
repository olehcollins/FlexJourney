# Database Migration Result

```bash
      dotnet ef database update                                                                                                                                                                                                                                                            ─╯
      Build started...
      Build succeeded.
      info: Microsoft.EntityFrameworkCore.Database.Command[20101]
            Executed DbCommand (23ms) [Parameters=[], CommandType='Text', CommandTimeout='30']
            SELECT EXISTS (
            SELECT 1 FROM pg_catalog.pg_class c
            JOIN pg_catalog.pg_namespace n ON n.oid=c.relnamespace
            WHERE n.nspname='public' AND
                  c.relname='__EFMigrationsHistory'
            )
      info: Microsoft.EntityFrameworkCore.Database.Command[20101]
            Executed DbCommand (4ms) [Parameters=[], CommandType='Text', CommandTimeout='30']
            SELECT "MigrationId", "ProductVersion"
            FROM "__EFMigrationsHistory"
            ORDER BY "MigrationId";
      info: Microsoft.EntityFrameworkCore.Database.Command[20101]
            Executed DbCommand (1ms) [Parameters=[], CommandType='Text', CommandTimeout='30']
            SELECT EXISTS (
            SELECT 1 FROM pg_catalog.pg_class c
            JOIN pg_catalog.pg_namespace n ON n.oid=c.relnamespace
            WHERE n.nspname='public' AND
                  c.relname='__EFMigrationsHistory'
            )
      info: Microsoft.EntityFrameworkCore.Database.Command[20101]
            Executed DbCommand (0ms) [Parameters=[], CommandType='Text', CommandTimeout='30']
            SELECT EXISTS (
            SELECT 1 FROM pg_catalog.pg_class c
            JOIN pg_catalog.pg_namespace n ON n.oid=c.relnamespace
            WHERE n.nspname='public' AND
                  c.relname='__EFMigrationsHistory'
            )
      info: Microsoft.EntityFrameworkCore.Database.Command[20101]
            Executed DbCommand (0ms) [Parameters=[], CommandType='Text', CommandTimeout='30']
            SELECT "MigrationId", "ProductVersion"
            FROM "__EFMigrationsHistory"
            ORDER BY "MigrationId";
      info: Microsoft.EntityFrameworkCore.Migrations[20402]
            Applying migration '20240902131212_UpdatedSchema'.
      Applying migration '20240902131212_UpdatedSchema'.
      info: Microsoft.EntityFrameworkCore.Database.Command[20101]
            Executed DbCommand (10ms) [Parameters=[], CommandType='Text', CommandTimeout='30']
            DROP TABLE "Users";
      info: Microsoft.EntityFrameworkCore.Database.Command[20101]
            Executed DbCommand (10ms) [Parameters=[], CommandType='Text', CommandTimeout='30']
            CREATE TABLE "Appointments" (
            "Id" uuid NOT NULL,
            "PatientName" text NOT NULL,
            "DoctorName" text NOT NULL,
            "AppointmentDate" timestamp with time zone NOT NULL,
            "Status" text NOT NULL,
            CONSTRAINT "PK_Appointments" PRIMARY KEY ("Id")
            );
      info: Microsoft.EntityFrameworkCore.Database.Command[20101]
            Executed DbCommand (16ms) [Parameters=[], CommandType='Text', CommandTimeout='30']
            CREATE TABLE "AspNetRoles" (
            "Id" text NOT NULL,
            "Name" character varying(256),
            "NormalizedName" character varying(256),
            "ConcurrencyStamp" text,
            CONSTRAINT "PK_AspNetRoles" PRIMARY KEY ("Id")
            );
      info: Microsoft.EntityFrameworkCore.Database.Command[20101]
            Executed DbCommand (3ms) [Parameters=[], CommandType='Text', CommandTimeout='30']
            CREATE TABLE "AspNetUsers" (
            "Id" text NOT NULL,
            "FirstName" text NOT NULL,
            "LastName" text NOT NULL,
            "DateAdded" timestamp with time zone NOT NULL,
            "ProfilePhotoPath" text NOT NULL,
            "UserName" character varying(256),
            "NormalizedUserName" character varying(256),
            "Email" character varying(256),
            "NormalizedEmail" character varying(256),
            "EmailConfirmed" boolean NOT NULL,
            "PasswordHash" text,
            "SecurityStamp" text,
            "ConcurrencyStamp" text,
            "PhoneNumber" text,
            "PhoneNumberConfirmed" boolean NOT NULL,
            "TwoFactorEnabled" boolean NOT NULL,
            "LockoutEnd" timestamp with time zone,
            "LockoutEnabled" boolean NOT NULL,
            "AccessFailedCount" integer NOT NULL,
            CONSTRAINT "PK_AspNetUsers" PRIMARY KEY ("Id")
            );
      info: Microsoft.EntityFrameworkCore.Database.Command[20101]
            Executed DbCommand (7ms) [Parameters=[], CommandType='Text', CommandTimeout='30']
            CREATE TABLE "AspNetRoleClaims" (
            "Id" integer GENERATED BY DEFAULT AS IDENTITY,
            "RoleId" text NOT NULL,
            "ClaimType" text,
            "ClaimValue" text,
            CONSTRAINT "PK_AspNetRoleClaims" PRIMARY KEY ("Id"),
            CONSTRAINT "FK_AspNetRoleClaims_AspNetRoles_RoleId" FOREIGN KEY ("RoleId") REFERENCES "AspNetRoles" ("Id") ON DELETE CASCADE
            );
      info: Microsoft.EntityFrameworkCore.Database.Command[20101]
            Executed DbCommand (3ms) [Parameters=[], CommandType='Text', CommandTimeout='30']
            CREATE TABLE "AspNetUserClaims" (
            "Id" integer GENERATED BY DEFAULT AS IDENTITY,
            "UserId" text NOT NULL,
            "ClaimType" text,
            "ClaimValue" text,
            CONSTRAINT "PK_AspNetUserClaims" PRIMARY KEY ("Id"),
            CONSTRAINT "FK_AspNetUserClaims_AspNetUsers_UserId" FOREIGN KEY ("UserId") REFERENCES "AspNetUsers" ("Id") ON DELETE CASCADE
            );
      info: Microsoft.EntityFrameworkCore.Database.Command[20101]
            Executed DbCommand (2ms) [Parameters=[], CommandType='Text', CommandTimeout='30']
            CREATE TABLE "AspNetUserLogins" (
            "LoginProvider" text NOT NULL,
            "ProviderKey" text NOT NULL,
            "ProviderDisplayName" text,
            "UserId" text NOT NULL,
            CONSTRAINT "PK_AspNetUserLogins" PRIMARY KEY ("LoginProvider", "ProviderKey"),
            CONSTRAINT "FK_AspNetUserLogins_AspNetUsers_UserId" FOREIGN KEY ("UserId") REFERENCES "AspNetUsers" ("Id") ON DELETE CASCADE
            );
      info: Microsoft.EntityFrameworkCore.Database.Command[20101]
            Executed DbCommand (5ms) [Parameters=[], CommandType='Text', CommandTimeout='30']
            CREATE TABLE "AspNetUserRoles" (
            "UserId" text NOT NULL,
            "RoleId" text NOT NULL,
            CONSTRAINT "PK_AspNetUserRoles" PRIMARY KEY ("UserId", "RoleId"),
            CONSTRAINT "FK_AspNetUserRoles_AspNetRoles_RoleId" FOREIGN KEY ("RoleId") REFERENCES "AspNetRoles" ("Id") ON DELETE CASCADE,
            CONSTRAINT "FK_AspNetUserRoles_AspNetUsers_UserId" FOREIGN KEY ("UserId") REFERENCES "AspNetUsers" ("Id") ON DELETE CASCADE
            );
      info: Microsoft.EntityFrameworkCore.Database.Command[20101]
            Executed DbCommand (3ms) [Parameters=[], CommandType='Text', CommandTimeout='30']
            CREATE TABLE "AspNetUserTokens" (
            "UserId" text NOT NULL,
            "LoginProvider" text NOT NULL,
            "Name" text NOT NULL,
            "Value" text,
            CONSTRAINT "PK_AspNetUserTokens" PRIMARY KEY ("UserId", "LoginProvider", "Name"),
            CONSTRAINT "FK_AspNetUserTokens_AspNetUsers_UserId" FOREIGN KEY ("UserId") REFERENCES "AspNetUsers" ("Id") ON DELETE CASCADE
            );
      info: Microsoft.EntityFrameworkCore.Database.Command[20101]
            Executed DbCommand (1ms) [Parameters=[], CommandType='Text', CommandTimeout='30']
            CREATE INDEX "IX_AspNetRoleClaims_RoleId" ON "AspNetRoleClaims" ("RoleId");
      info: Microsoft.EntityFrameworkCore.Database.Command[20101]
            Executed DbCommand (1ms) [Parameters=[], CommandType='Text', CommandTimeout='30']
            CREATE UNIQUE INDEX "RoleNameIndex" ON "AspNetRoles" ("NormalizedName");
      info: Microsoft.EntityFrameworkCore.Database.Command[20101]
            Executed DbCommand (1ms) [Parameters=[], CommandType='Text', CommandTimeout='30']
            CREATE INDEX "IX_AspNetUserClaims_UserId" ON "AspNetUserClaims" ("UserId");
      info: Microsoft.EntityFrameworkCore.Database.Command[20101]
            Executed DbCommand (1ms) [Parameters=[], CommandType='Text', CommandTimeout='30']
            CREATE INDEX "IX_AspNetUserLogins_UserId" ON "AspNetUserLogins" ("UserId");
      info: Microsoft.EntityFrameworkCore.Database.Command[20101]
            Executed DbCommand (1ms) [Parameters=[], CommandType='Text', CommandTimeout='30']
            CREATE INDEX "IX_AspNetUserRoles_RoleId" ON "AspNetUserRoles" ("RoleId");
      info: Microsoft.EntityFrameworkCore.Database.Command[20101]
            Executed DbCommand (1ms) [Parameters=[], CommandType='Text', CommandTimeout='30']
            CREATE INDEX "EmailIndex" ON "AspNetUsers" ("NormalizedEmail");
      info: Microsoft.EntityFrameworkCore.Database.Command[20101]
            Executed DbCommand (1ms) [Parameters=[], CommandType='Text', CommandTimeout='30']
            CREATE UNIQUE INDEX "UserNameIndex" ON "AspNetUsers" ("NormalizedUserName");
      info: Microsoft.EntityFrameworkCore.Database.Command[20101]
            Executed DbCommand (0ms) [Parameters=[], CommandType='Text', CommandTimeout='30']
            INSERT INTO "__EFMigrationsHistory" ("MigrationId", "ProductVersion")
            VALUES ('20240902131212_UpdatedSchema', '8.0.8');
      Done.
```
