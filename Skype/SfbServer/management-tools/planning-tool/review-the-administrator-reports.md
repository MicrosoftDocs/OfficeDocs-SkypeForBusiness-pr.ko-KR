---
title: 비즈니스용 Skype Server 2015의 관리자 보고서 검토
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 22d480ea-cd64-4d09-99fe-96e997570844
description: 관리자 보고서는 배포 및 작업에 대 한 자세한 정보입니다. 디자인 사이트에 표시 된 선택 사항에 따라 보고서가 생성 됩니다. 디자이너는 네트워크 다이어그램을 편집 하 고 서버, 풀 및 부하 분산 장치에 대 한 전체 IP 주소와 Fqdn (정규화 된 도메인 이름)을 정의 하 여 관리자 보고서에 값을 추가할 수 있습니다.
ms.openlocfilehash: 22b3628c5c2a499d57a6bfdd1d90fe3b79b90e85
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191232"
---
# <a name="review-the-administrator-reports-in-skype-for-business-server-2015"></a><span data-ttu-id="93df6-105">비즈니스용 Skype Server 2015의 관리자 보고서 검토</span><span class="sxs-lookup"><span data-stu-id="93df6-105">Review the Administrator Reports in Skype for Business Server 2015</span></span>

<span data-ttu-id="93df6-106">관리자 보고서는 배포 및 작업에 대 한 자세한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="93df6-106">The Administrator Reports are detailed information for deployment and operations.</span></span> <span data-ttu-id="93df6-107">**디자인 사이트**에 표시 된 선택 사항에 따라 보고서가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93df6-107">The reports are generated based on the selections marked in **Design Sites**.</span></span> <span data-ttu-id="93df6-108">디자이너는 네트워크 다이어그램을 편집 하 고 서버, 풀 및 부하 분산 장치에 대 한 전체 IP 주소와 Fqdn (정규화 된 도메인 이름)을 정의 하 여 관리자 보고서에 값을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93df6-108">The designer can further add value to the Administrator Reports by editing the network diagrams and defining the complete IP addresses and fully qualified domain names (FQDNs) for servers, pools, and load balancers.</span></span>

<span data-ttu-id="93df6-109">관리자 보고서 기능을 사용 하 여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93df6-109">The Administrator reports feature allows you to:</span></span>

- [<span data-ttu-id="93df6-110">요약 보고서 검토</span><span class="sxs-lookup"><span data-stu-id="93df6-110">Review the Summary Report</span></span>](review-the-administrator-reports.md#Summary_report)

- [<span data-ttu-id="93df6-111">인증서 보고서 검토</span><span class="sxs-lookup"><span data-stu-id="93df6-111">Review the Certificates Report</span></span>](review-the-administrator-reports.md#Certificates_Report)

- [<span data-ttu-id="93df6-112">방화벽 보고서 검토</span><span class="sxs-lookup"><span data-stu-id="93df6-112">Review the Firewall Report</span></span>](review-the-administrator-reports.md#Firewall_report)

- [<span data-ttu-id="93df6-113">DNS 보고서 검토</span><span class="sxs-lookup"><span data-stu-id="93df6-113">Review the DNS Report</span></span>](review-the-administrator-reports.md#DNS_Report)

## <a name="review-the-summary-report"></a><span data-ttu-id="93df6-114">요약 보고서 검토</span><span class="sxs-lookup"><span data-stu-id="93df6-114">Review the Summary Report</span></span>
<span data-ttu-id="93df6-115"><a name="Summary_report"> </a></span><span class="sxs-lookup"><span data-stu-id="93df6-115"></span></span>

<span data-ttu-id="93df6-116">비즈니스용 Skype 관리자 보고서는 디자인을 자세히 문서화 하는 네 가지 중요 한 보고서입니다.</span><span class="sxs-lookup"><span data-stu-id="93df6-116">The Skype for Business Administrator Report is the first of four valuable reports that document your design in detail.</span></span> <span data-ttu-id="93df6-117">이 보고서의 정보와 나머지 세 개의 관련 보고서는 정보 기술 팀에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="93df6-117">The information in this report, and the other three associated reports, is useful for your Information Technology Teams:</span></span>

![일반 요약 관리 보고서](../../media/General_Summary_Report_Admin_Report.png)

<span data-ttu-id="93df6-119">요약 보고서에는 Edge 네트워크와 연결 된 일반 구성 정보가 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93df6-119">The Summary Report lists general configuration information associated with your Edge network.</span></span> <span data-ttu-id="93df6-120">위치, FQDN (정규화 된 도메인 이름) 및 IP 주소, 네트워크 유형, 주어진 역할에 해당 하는 설명이 문서화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93df6-120">The location, fully qualified domain name (FQDN) and IP address, type of network, and comments specific to a given role are documented.</span></span>

<span data-ttu-id="93df6-121">인프라를 배포 하 고, 관리 하 고, 유지 관리 하는 각 팀은 디자이너와 정확성에 대 한 요약 보고서를 검토 하 고 오류를 최소화 하는 것이 아닌지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93df6-121">The designer and each of the teams that will deploy, manage, and maintain the infrastructure should review the summary report for accuracy and to make sure that errors are at a minimum.</span></span>

<span data-ttu-id="93df6-122">다음과 같은 자세한 보고서를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93df6-122">You can also view more detailed reports:</span></span>

- <span data-ttu-id="93df6-123">인증서 보고서</span><span class="sxs-lookup"><span data-stu-id="93df6-123">Certificates Report</span></span>

- <span data-ttu-id="93df6-124">방화벽 보고서</span><span class="sxs-lookup"><span data-stu-id="93df6-124">Firewall Report</span></span>

- <span data-ttu-id="93df6-125">DNS 보고서</span><span class="sxs-lookup"><span data-stu-id="93df6-125">DNS Report</span></span>

## <a name="review-the-certificates-report"></a><span data-ttu-id="93df6-126">인증서 보고서 검토</span><span class="sxs-lookup"><span data-stu-id="93df6-126">Review the Certificates Report</span></span>
<span data-ttu-id="93df6-127"><a name="Certificates_Report"> </a></span><span class="sxs-lookup"><span data-stu-id="93df6-127"></span></span>

<span data-ttu-id="93df6-128">인증서 보고서에는 권장 되는 비즈니스용 Skype 서버 2015 배포에 필요한 모든 인증서가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93df6-128">The Certificates Report contains all certificates that are required in the recommended Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="93df6-129">계획 도구는 입력 된 주체 이름 및 주체 대체 이름에 대 한 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="93df6-129">The Planning Tool accounts for the subject names and subject alternative names that are entered.</span></span> <span data-ttu-id="93df6-130">편집 되지 않은 상태로 유지 되는 기본 텍스트는 인증서 요청 및 발급을 담당 하는 팀의 잠재적인 챌린지를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93df6-130">Default text that is left unedited may represent a potential challenge for the team responsible for requesting and issuing the certificates.</span></span> <span data-ttu-id="93df6-131">또한 인증서 정보에는 일반적으로 인증서를 발급할 수 있는 위치에 대 한 정보도 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93df6-131">Certificate information also contains information about where the certificate can typically be issued from.</span></span> <span data-ttu-id="93df6-132">인프라에 내부 PKI (공개 키 인프라)가 없으면 공용 인증서 공급자를 통해 모든 인증서를 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93df6-132">If the infrastructure does not have an internal public key infrastructure (PKI) in place, all certificates can be requested through a public certificate provider.</span></span> <span data-ttu-id="93df6-133">EKU (확장 키 용도) 및 보고서의 필드에 할당은 각 인증서의 용도와 위치를 이해 하는 데 매우 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="93df6-133">Extended key usages (EKU) and Assign To fields in the report are very helpful in understanding what the purpose and location for each certificate should be.</span></span>

![인증서 관리 보고서](../../media/Certificates_Report_Admin_Report.png)

<span data-ttu-id="93df6-135">신중 하 게 검토 하 고 배포에서 각 인증서의 용도와 목적을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93df6-135">Carefully review, and be sure to understand, the use and purpose of each certificate in the deployment.</span></span> <span data-ttu-id="93df6-136">인증서가 수행 하는 작업에 대 한 질문이 있는 경우 어떤 서버나 서비스와 통신 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="93df6-136">If there is a question about what a certificate does, determine which server or service is talking to what.</span></span> <span data-ttu-id="93df6-137">비즈니스용 Skype Server 2015의 인증서는 두 가지 주요 목적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93df6-137">Certificates in Skype for Business Server 2015 are used for two primary purposes:</span></span>

- <span data-ttu-id="93df6-138">MTLS (상호 전송 계층 보안)-통신과 관련 된 컴퓨터는 각각 자신의 id를 다른 컴퓨터에 증명 하는 인증서를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="93df6-138">Mutual Transport Layer Security (MTLS) - The computers involved in the communication each present a certificate that proves their identity to another computer.</span></span> <span data-ttu-id="93df6-139">이를 서버 인증 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="93df6-139">This is known as server authentication.</span></span> <span data-ttu-id="93df6-140">각 컴퓨터가 다른 컴퓨터의 id를 신뢰 해야 통신을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93df6-140">Communication cannot begin until each computer trusts the other computer's identity.</span></span>

- <span data-ttu-id="93df6-141">암호화-암호화 (보안 소켓 계층 또는 SSL, 전송 계층 보안 또는 TLS)는 통신을 보호 하 고, 개인 정보를 보호 하 고, 신뢰할 수 있는 통신 및 공동 작업 시스템을 만드는 데 도움이 되는 중요 한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="93df6-141">Encryption - Encryption (Secure Sockets Layer, or SSL, and Transport Layer Security, or TLS) is a critical means to help secure communications, help ensure privacy, and to create a trusted communications and collaboration system.</span></span>

## <a name="review-the-firewall-report"></a><span data-ttu-id="93df6-142">방화벽 보고서 검토</span><span class="sxs-lookup"><span data-stu-id="93df6-142">Review the Firewall Report</span></span>
<span data-ttu-id="93df6-143"><a name="Firewall_report"> </a></span><span class="sxs-lookup"><span data-stu-id="93df6-143"></span></span>

<span data-ttu-id="93df6-144">비즈니스용 Skype 서버 2015에는 잠재적으로 복잡 한 방화벽 규칙 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93df6-144">Skype for Business Server 2015 has a potentially complex set of firewall rules.</span></span> <span data-ttu-id="93df6-145">계획 도구는 디자이너의 입력 기준에 따라 모든 방화벽 요구 사항에 대 한 세부 정보를 정의 하는 보고서를 생성 하 여 이러한 복잡성을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="93df6-145">The Planning Tool reduces this complexity by generating a report that defines in detail all firewall requirements, based on the designer's input criteria.</span></span> <span data-ttu-id="93df6-146">IT 방화벽 관리자가이 보고서를 사용 하 여 필요한 규칙을 구성 하 고 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93df6-146">The IT firewall administrator will be able to use this report to configure and define the necessary rules.</span></span>

<span data-ttu-id="93df6-147">방화벽 관리의 관점에서 보고서를 검토 하 여 종료 되는 방화벽 규칙과 충돌이 없는지, 위반 될 수 있는 정책이 나 절차가 없는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93df6-147">From the standpoint of firewall management, the report should be carefully reviewed to make sure that there are no conflicts with exiting firewall rules and that there are no policies or procedures that might be violated.</span></span>

![방화벽 관리 보고서](../../media/Firewall_Report_Admin_Report.png)

## <a name="review-the-dns-report"></a><span data-ttu-id="93df6-149">DNS 보고서 검토</span><span class="sxs-lookup"><span data-stu-id="93df6-149">Review the DNS Report</span></span>
<span data-ttu-id="93df6-150"><a name="DNS_Report"> </a></span><span class="sxs-lookup"><span data-stu-id="93df6-150"></span></span>

<span data-ttu-id="93df6-151">관리자 보고서의 일부인 DNS 보고서는 내부, 주변, 외부 네트워크에서 DNS (Domain Name System)에 대해 권장 되는 항목과 알려진 항목을 모두 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="93df6-151">The DNS Report, which is part of the Administrator Report, details all of the recommended and known entries for the Domain Name System (DNS) in the internal, perimeter, and external networks.</span></span> <span data-ttu-id="93df6-152">디자이너가 네트워크 다이어그램에 대 한 편집을 완료 하 고 모든 IP 주소와 Fqdn (정규화 된 도메인 이름)이 해당 프로덕션 값에 정의 되어 있으면 DNS 보고서가 우수한 구성 리소스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="93df6-152">If the designer has completed the edits to the network diagram, and all IP addresses and fully qualified domain names (FQDNs) are defined to their production values, the DNS Report provides an excellent configuration resource.</span></span> <span data-ttu-id="93df6-153">이 보고서는 운영 문제 해결 문서 역할을 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93df6-153">This report can also serve as an operational troubleshooting document.</span></span>

![DNS 관리 보고서](../../media/DNS_Report_Admin_Report.png)

<span data-ttu-id="93df6-155">Dns 관리 팀에서 DNS 보고서를 검토 하 여 배포 중에 발생 하는 문제가 없는지, 문제 해결 세션을 복잡 하 게 만들 수 있는지 철저히 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93df6-155">You should have your DNS management team review the DNS Report thoroughly to make sure that there are no errors that may cause difficulty during deployment or that may complicate a troubleshooting session.</span></span>

## <a name="see-also"></a><span data-ttu-id="93df6-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="93df6-156">See also</span></span>
<span data-ttu-id="93df6-157"><a name="DNS_Report"> </a></span><span class="sxs-lookup"><span data-stu-id="93df6-157"></span></span>

[<span data-ttu-id="93df6-158">관리자 보고서 검토</span><span class="sxs-lookup"><span data-stu-id="93df6-158">Reviewing the Administrator Reports</span></span>](https://technet.microsoft.com/library/1dee56a9-a033-4201-9765-e3469bd7d3e3.aspx)
