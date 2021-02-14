---
title: 환자 앱 개요
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: FHIR API를 사용하여 Electronic Healthcare Records를 Microsoft Teams Patients 앱에 통합하는 방법을 배워야 합니다.
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 594375959a8cd7cbbfc21c6b9d5ceb6c0f8a8dac
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803546"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a>Microsoft Teams에 전자 의료 레코드 통합

> [!NOTE]
> 2020년 10월 30일부로 환자 앱은 사용 중지되고 Teams의 [목록](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 앱으로 대체됩니다. 환자 앱 데이터는 팀을 백업하는 Office 365 그룹의 그룹 사서함에 저장됩니다. 환자 앱과 연결된 모든 데이터는 이 그룹에 유지되지만 사용자 인터페이스를 통해 더 이상 액세스할 수 없습니다. 사용자는 목록 앱을 사용하여 목록을 다시 [만들 수 있습니다.](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)
>
>목록을 사용하여 의료 조직의 관리 팀은 라운드 및학 간 팀 모임에서 일반 환자 모니터링에 이르는 시나리오에 대한 환자 목록을 만들 수 있습니다. 시작을 위해 목록에서 환자 서식 파일을 확인해 하세요. 조직에서 목록 앱을 관리하는 방법에 대한 자세한 내용은 목록 앱 [관리를 참조하세요.](../../manage-lists-app.md)

이 문서는 의료 정보 시스템 위에 FHIR API를 사용하여 Microsoft Teams에 연결하는 데 관심이 있는 일반 의료 IT 개발자를 위한 것입니다. 이렇게 하면 의료 조직의 요구와 일치하는 관리 조정 시나리오를 사용할 수 있습니다.

연결된 문서에서는 Microsoft Teams Patients 앱에 대한 FHIR 인터페이스 사양을 문서화하고, 다음 섹션에서는 FHIR 서버를 설정하고 개발 환경 또는 테넌트에서 Patients 앱에 연결하는 데 필요한 것을 설명합니다. 또한 지원되는 옵션 중 하나에 해당해야 하는 선택한 FHIR 서버의 설명서를 잘 알고 있어야 합니다.

- Datica(CMI [](https://datica.com/compliant-managed-integration/) 제품을 통해)
- Infor Cloverleaf(Infor [FHIR 브리지를 통해)](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html)
- [Redox(R^FHIR 서버를 통해)](https://www.redoxengine.com/fhir/)
- [Dapasoft(FHIR의 Corolar를 통해)](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/)

> [!NOTE]
> 이 프로세스에는 Microsoft Teams 관리 센터 또는 PowerShell cmdlet을 사용하여 기능을 사용하도록 설정하는 단계가 포함되어 있지 않습니다. 구성은 FHIR 서버/서비스 쪽 및 Patients 앱 클라이언트에서 전적으로 수행됩니다.

아래 그림은 Patients 앱의 아키텍처입니다.

![환자 앱 아키텍처 다이어그램](../../media/patients-app-architecture.png)

다음 섹션에서는 환자 앱과 통합하기 위해 FHIR 서버(또는 EHR 사용 FHIR API)가 충족해야 하는 환자 앱에 대한 FHIR 전용 데이터 액세스 계층의 요구 사항을 설명합니다.

- 사용자 인증에 대한 기대치
- 통합 인터페이스의 기능 및 기술 요구 사항
- 성능 및 안정성에 대한 기대치
- 환자 앱에 지원될 FHIR 리소스에 대한 기대치
- 통합 프로세스 및 예상 계약 모델
- FHIR 및 환자 앱에 직면한 몇 가지 일반적인 과제를 시작하는 방법
- 환자 앱의 다음에 실행하기 위한 향후 요구 사항

> [!NOTE]
> 다음 섹션에서 "partner" 또는 "Interop partner"라는 단어는 FHIR을 통해 환자 앱에 대한 EHR 시스템에 통합할 수 있는 모든 제3자 조직을 참조하는 데 사용되어 나열된 사양과 일치하게 FHIR 서버를 구현합니다.

## <a name="functional-and-technical-requirements"></a>기능 및 기술 요구 사항  

### <a name="authentication"></a>인증  

사용자 수준  권한 부여를 지원하지 않는 앱 수준 권한 부여는 EHR 시스템에서 사용자 수준 권한 부여를 구현할 수 있는 경우에도 FHIR을 통해 데이터 변환을 수행하고 EHR 데이터에 대한 연결을 노출하는 가장 일반적으로 지원되는 방식입니다. Interop Service(파트너)는 EHR 데이터에 대한 상승된 액세스를 얻게 하며, 적절한 FHIR 리소스와 동일한 데이터를 노출하면 Interop Service 또는 플랫폼과 통합된 Interop Service Consumer(환자 앱)에 전달된 권한 부여 컨텍스트가 없습니다. 환자 앱은 사용자 수준 권한 부여를 적용할 수 없지만 Patients 앱과 Interop 파트너의 서비스 간에 애플리케이션 인증을 지원합니다.

애플리케이션-애플리케이션 인증 모델은 아래에 설명되어 있습니다.

서비스 대 서비스 인증은 OAuth 2.0 클라이언트 자격 증명 [흐름을 통해 수행해야 합니다.](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/) 파트너 서비스는 다음을 제공해야 합니다.

1. 파트너 서비스를 사용하면 환자 앱이 파트너와 계정을 만들 수 있습니다. 이를 통해 환자 앱은 파트너의 인증 서버에서 인증 등록 포털을 통해 관리되는 client_id client_secret 및 앱을 생성하고 소유할 수 있습니다.

2. 파트너 서비스는 제공된 클라이언트 자격 증명을 수락하고 확인(인증)하는 인증/권한 부여 시스템을 소유하며 아래 설명된 바와 같이 범위에 테넌트 힌트를 사용하여 액세스 토큰을 다시 제공합니다.

3. 보안상의 이유로 또는 비밀 위반의 경우 Patients 앱은 비밀을 다시 생성하고 이전 비밀을 무효화하거나 삭제할 수 있습니다(예: Azure Portal - AAD 앱 등록에서 동일하게 사용 가능).

4. 준수 문을 호스팅하는 메타데이터 엔드포인트는 인증되지 않고 인증 토큰 없이 액세스할 수 있습니다.

5. 파트너 서비스는 환자 앱에 대한 토큰 엔드포인트를 제공하여 클라이언트 자격 증명 흐름을 사용하여 액세스 토큰을 요청합니다. 권한 부여 서버에 따라 토큰 URL은 다음 예제와 같은 FHIR 서버의 메타데이터에서 페치된 FHIR 준수(기능) 문의 일부입니다.

    ```
    {
        "resourceType": "CapabilityStatement",
        .
        .
        .
        "rest": [
            {
                "mode": "server",
                "security": {
                    "extension": [
                        {
                            "extension": [
                                {
                                    "url": "token",
                                    "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/token"
                                },
                                {
                                    "url": "authorize",
                                    "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/authorize"
                                }
                            ],
                            "url": "http://fhir-registry.smarthealthit.org/StructureDefinition/oauth-uris"
                        }
                    ],
                    "service": [
                        {
                            "coding": [
                                {
                                    "system": "https://hl7.org/fhir/ValueSet/restful-security-service",
                                    "code": "OAuth"
                                }
                            ]
                        }
                    ]
                },
                .
                .
                .
            }
        ]
    }
    ```

액세스 토큰에 대한 요청은 다음 매개 변수로 구성됩니다.

```http
POST /token HTTP/1.1
Host: authorization-server.com

grant-type=client_credentials
&client_id=xxxxxxxxxx
&client_secret=xxxxxxxxxx
```

파트너 서비스는 파트너 client_id client_secret Auth 등록 포털을 통해 관리되는 환자 앱에 대한 데이터 및 서비스를 제공합니다. 파트너 서비스는 클라이언트 자격 증명 흐름을 사용하여 액세스 토큰을 요청하는 엔드포인트를 제공합니다. 성공적인 응답에는 매개 변수 token_type, access_token 및 expires_in 포함되어야 합니다.

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a>라우팅: 공급자 엔드포인트에 AAD 테넌트 매핑

환자 앱은 단일 엔드포인트를 통해 파트너 서비스에 연결합니다. 파트너 서비스는 파트너 서비스가 작업하는 각 Microsoft 고객(AAD 테넌트 ID)을 해당 FHIR 서버(의료 공급자)에 매핑하는 메커니즘을 소유하고 유지 관리합니다.

공급자 엔드포인트에 AAD 테넌트 매핑은 AAD 테넌트 ID(GUID)를 사용합니다. 환자 앱은 각 요청에 대한 액세스 토큰을 요청하는 동안 범위에서 테넌트 ID를 전달합니다. 파트너 서비스는 테넌트 ID를 공급자 엔드포인트로 매핑하고 테넌트 ID에 따라 공급자 엔드포인트로 요청을 리디렉션합니다. 이를 위해 파트너는 수동으로 또는 포털을 통해 Interop 플랫폼에 공급자 조직의 온보드의 일부로 구성을 지원합니다.

인증 및 라우팅 워크플로는 다음과 같습니다.

![인증 및 라우팅 워크플로 다이어그램](../../media/Patient-app-6.png)

1. 전송하여 앱 액세스 토큰에 대한 요청:
 
    ```
    {   grant_type: client_credentials,
        client_id: xxxxxx, 
        client_secret: xxxxxx,
        scope: {Provider Identifier, Ex: tenant ID}
    }
    ```

2. 앱 토큰으로 회신:

    ```
    {  access_token: {JWT, with scope: tenant ID},
       expires_in: 156678,
       token_type: "Bearer",
    }
    ```

3. Access 토큰을 사용하여 보호된 데이터를 요청합니다.

4. 권한 부여 메시지: 범위의 테넌트 ID에서 라우팅할 적절한 FHIR 서버를 선택합니다.

5. 앱 토큰으로 인증한 후 인증된 FHIR 서버에서 앱 보호 데이터를 전송합니다.

## <a name="interfaces"></a>인터페이스

환자 앱에서 사용하는 특정 호출 및 필드는 다음 문서에 설명되어 있습니다. FHIR 서버/FHIR API에 적용할 인터페이스를 선택합니다.

- [DSTU2 인터페이스 사양](dstu2-interface.md)
- [STU3 인터페이스 사양](stu3-interface.md)

## <a name="performance-and-reliability"></a>성능 및 안정성

Patients 앱은 비공개 미리 보기 상태인 반면 종단적 성능에 대한 보장은 없습니다. 성능의 요인에는 워크플로와 관련된 모든 홉의 상대적 대기 시간(상태 시스템 환경의 EHR에서 시작하여 FHIR 서버를 포함한 Interop 파트너 및 해당fra, Office 365 에코시스템 및 환자 앱까지)에 대한 상대적 대기 시간이 포함됩니다.

![Interop 파트너 성능 그림](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a>FHIR 시작  

FHIR을 사용하는 경우 Microsoft Teams EHR 통합 인터페이스에 노출할 수 있는 FHIR 서버에 쉽게 액세스해야 하는 경우 Microsoft는 모든 개발자가 사용할 수 있는 오픈 소스 FHIR 서버를 제공합니다. Microsoft에서 사용할 수 있는 오픈 소스 FHIR Server에 대해 자세히 알아보고 조직에 배포하는 방법을 알아보는 [Azure용 FHIR Server란?](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) 문서를 참조하세요.

HSPC Open 샌드박스 EHR 환경을 사용하여 열린 FHIR 서버를 지원하는 EHR을 만들고 이 환경을 사용하여 Patients 앱을 사용할 수 있습니다. HSPC 샌드박스 설명서를 [읽어보는 것이 좋습니다.](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox) 샌드박스는 환자를 만들고, 추가하고, 편집하는 간편하고 UI 지향적인 사용자 친화적인 방법을 제공할 뿐만 아니라 시작하는 데 필요한 몇 가지 샘플을 제공합니다. 
