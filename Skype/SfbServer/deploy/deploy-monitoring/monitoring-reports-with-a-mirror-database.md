---
title: 모니터링 보고서를 데이터베이스의 미러 데이터베이스와 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
description: '요약: 모니터링 보고서를 모니터링 보고서에서 사용하는 미러 데이터베이스와 비즈니스용 Skype 서버.'
ms.openlocfilehash: ecdf630f6839fa65bf163715e473a3a37cdbcece
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60014402"
---
# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server"></a>모니터링 보고서를 데이터베이스의 미러 데이터베이스와 비즈니스용 Skype 서버 
 
**요약:** 모니터링 보고서를 모니터링 보고서에서 사용하는 미러 데이터베이스와 비즈니스용 Skype 서버.
  
## <a name="monitor-reports-with-a-mirror-database"></a>미러 데이터베이스를 통해 보고서 모니터링

모니터링 데이터베이스에 대해 미러를 구성하면 장애 조치(failover)가 발생하는 경우 해당 미러 데이터베이스가 기본 데이터베이스로 사용하게 됩니다. 그러나 모니터링 보고서를 비즈니스용 Skype 서버 장애 조치(failover)가 발생하는 경우 모니터링 보고서가 미러 데이터베이스에 연결되지 않는 것일 수 있습니다. 이는 모니터링 보고서를 설치할 때 기본 데이터베이스의 위치만 지정하기 때문에입니다. 미러 데이터베이스의 위치를 지정하지 않습니다.
  
모니터링 보고서가 미러 데이터베이스로 자동 장애 조치(failover)를 수행하려면 모니터링 보고서에서 사용되는 두 데이터베이스(통화 정보 기록 데이터용 데이터베이스 하나와 QoE(QoE)에 대한 다른 데이터베이스)에 미러 데이터베이스를 "장애 조치(failover) 파트너"로 추가해야 합니다. 이 단계는 모니터링 보고서를 설치한 후에 수행해야 합니다. 이러한 두 데이터베이스에서 사용하는 연결 문자열 값을 수동으로 편집하여 장애 조치 파트너 정보를 추가할 수 있습니다. 이렇게 하려면 다음 절차를 완료합니다.
  
1. 이 Internet Explorer 사용하여 SQL Server Reporting Services **를** 열 수 있습니다. Reporting Services 홈 페이지 URL에는 다음이 포함됩니다.
    
   - **http:** prefix.
    
   - Reporting Services가 설치된 컴퓨터의 FQDN(정식 도메인 이름)입니다(예: `atl-sql-001.litwareinc.com` ).
    
   - 문자열 **/Reports_.**
    
   - 모니터링 보고서가 설치된 데이터베이스 인스턴스의 이름(예: **archinst)입니다.**
    
     예를 들어 컴퓨터에 SQL Server Reporting Services 모니터링 보고서에서 데이터베이스 인스턴스 보관을 사용하는 경우 홈 페이지 URL은 다음과 `atl-sql-001.litwareinc.com` 같습니다.
    
     `http://atl-sql-001.litwareinc.com/Reports_archinst`
    
2. Reporting Services 홈 페이지에 액세스한 후 **ServerReports** 를 클릭하고 를 **Reports_Content.** 이 페이지로 이동하여 Reports_Content **모니터링** 보고서의 비즈니스용 Skype 서버 이동합니다.
    
3. 페이지 **Reports_Content** **CDRDB** 데이터 원본을 클릭합니다.
    
4. **CDRDB** 페이지의 **속성 탭에서** 연결 문자열로 레이블이 붙은 텍스트 **상자를 확인합니다.** 현재 연결 문자열은 다음과 유사합니다.
    
    Data source=(local)\archinst;initial catalog=LcsCDR
    
5. 미러 데이터베이스에 대한 서버 이름 및 데이터베이스 인스턴스를 포함하려면 연결 문자열을 편집합니다. 예를 들어 서버의 이름이 atl-mirror-001인 경우 미러 데이터베이스가 보관 인스턴스에 있는 경우 다음 구문을 사용하여 미러 데이터베이스를 지정하기 위해 추가해야 합니다.
    
    장애 조치 파트너=atl-mirror-001\archinst
    
    편집한 연결 문자열은 다음과 같습니다.
    
    Data source=(local)\archinst; 장애 조치 파트너=atl-mirror-001\archinst;initial catalog=LcsCDR
    
6. 연결 문자열을 업데이트한 후 적용을 **클릭합니다.**
    
7. **CDRDB 페이지에서** 페이지 Reports_Content **클릭합니다.** **QMSDB 데이터** 원본을 클릭한 다음 QoE 데이터베이스의 연결 문자열을 편집합니다. 예제:
    
    `Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics`
    
8. **적용** 을 클릭합니다.
    
## <a name="see-also"></a>참고 항목

[모니터링 보고서 설치 비즈니스용 Skype 서버](install-monitoring-reports.md)
  
[2016에서 모니터링 보고서 비즈니스용 Skype 서버](../../manage/health-and-monitoring/monitoring-reports.md)
