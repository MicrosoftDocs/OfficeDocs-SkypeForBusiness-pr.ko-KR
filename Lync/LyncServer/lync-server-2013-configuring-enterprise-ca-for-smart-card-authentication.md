---
title: 'Lync Server 2013: 스마트 카드 인증용으로 엔터프라이즈 CA 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Enterprise CA for smart card authentication
ms:assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308571(v=OCS.15)
ms:contentKeyID: 54973692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abfbbb7a7f7787ab5490db1542c4435368a84ca0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532565"
---
# <a name="configuring-enterprise-ca-for-smart-card-authentication-in-lync-server-2013"></a><span data-ttu-id="924f6-102">Lync Server 2013에서 스마트 카드 인증용 엔터프라이즈 CA 구성</span><span class="sxs-lookup"><span data-stu-id="924f6-102">Configuring Enterprise CA for smart card authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="924f6-103">_**마지막으로 수정 된 항목:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="924f6-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="924f6-104">다음 섹션에서는 스마트 카드 인증을 지원 하도록 엔터프라이즈 루트 CA (인증 기관)를 구성 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="924f6-104">The following section describes how to configure an Enterprise Root Certification Authority (CA) to support smart card authentication.</span></span> <span data-ttu-id="924f6-105">엔터프라이즈 루트 CA를 설치 하는 방법에 대 한 자세한 내용은에서 엔터프라이즈 루트 인증 기관 설치를 참조 하십시오 [https://go.microsoft.com/fwlink/p/?LinkID=313364](https://go.microsoft.com/fwlink/p/?linkid=313364) .</span><span class="sxs-lookup"><span data-stu-id="924f6-105">For information on how to install an Enterprise Root CA, see Install an Enterprise Root Certification Authority at [https://go.microsoft.com/fwlink/p/?LinkID=313364](https://go.microsoft.com/fwlink/p/?linkid=313364).</span></span>

<div>

## <a name="configuring-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a><span data-ttu-id="924f6-106">스마트 카드 인증을 지원 하도록 엔터프라이즈 루트 인증 기관 구성</span><span class="sxs-lookup"><span data-stu-id="924f6-106">Configuring an Enterprise Root Certificate Authority to Support Smart Card Authentication</span></span>

<span data-ttu-id="924f6-107">다음 단계에서는 스마트 카드 인증을 지원 하도록 엔터프라이즈 루트 CA를 구성 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="924f6-107">The following steps describe how to configure an Enterprise Root CA to support Smart Card Authentication:</span></span>

1.  <span data-ttu-id="924f6-108">도메인 관리자 계정을 사용 하 여 엔터프라이즈 CA 컴퓨터에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="924f6-108">Log in to the Enterprise CA computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="924f6-109">System Manager를 시작 하 고 인증 기관 웹 등록 역할이 설치 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="924f6-109">Launch System Manager, and verify that the Certificate Authority Web Enrollment role is installed.</span></span>

3.  <span data-ttu-id="924f6-110">**관리 도구** 메뉴에서 **인증 기관** 관리 콘솔을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="924f6-110">From the **Administrative Tools** menu, open the **Certification Authority** management console.</span></span>

4.  <span data-ttu-id="924f6-111">탐색 창에서 **인증 기관을**확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="924f6-111">In the Navigation pane, expand **Certification Authority**.</span></span>

5.  <span data-ttu-id="924f6-112">**인증서 템플릿을**마우스 오른쪽 단추로 클릭 하 고 **새로 만들기**를 선택한 다음 **발급할 인증서 템플릿을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="924f6-112">Right click on **Certificate Templates**, select **New**, then select **Certificate Template to Issue**.</span></span>

6.  <span data-ttu-id="924f6-113">**등록 에이전트**, **스마트 카드 사용자**및 **스마트 카드 로그온**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="924f6-113">Select **Enrollment Agent**, **Smartcard User**, and **Smartcard Logon**.</span></span>

7.  <span data-ttu-id="924f6-114">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="924f6-114">Click **OK**.</span></span>

8.  <span data-ttu-id="924f6-115">**인증서 템플릿을**마우스 오른쪽 단추로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="924f6-115">Right click on **Certificate Templates**.</span></span>

9.  <span data-ttu-id="924f6-116">**관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="924f6-116">Select **Manage**.</span></span>

10. <span data-ttu-id="924f6-117">스마트 카드 사용자 서식 파일의 속성을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="924f6-117">Open the properties of the Smartcard User template.</span></span>

11. <span data-ttu-id="924f6-118">**보안** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="924f6-118">Click on the **Security** tab.</span></span>

12. <span data-ttu-id="924f6-119">사용 권한을 다음과 같이 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="924f6-119">Change the permissions as follows:</span></span>
    
      - <span data-ttu-id="924f6-120">읽기/등록 (허용) 권한을 사용 하 여 개별 사용자 AD 계정을 추가 하거나</span><span class="sxs-lookup"><span data-stu-id="924f6-120">Add individual user AD accounts with Read/Enroll (Allow) permissions, or</span></span>
    
      - <span data-ttu-id="924f6-121">읽기/등록 (허용) 권한을 가진 스마트 카드 사용자를 포함 하는 보안 그룹을 추가 하거나</span><span class="sxs-lookup"><span data-stu-id="924f6-121">Add a security group containing smart card users with Read/Enroll (Allow) permissions, or</span></span>
    
      - <span data-ttu-id="924f6-122">읽기/등록 (허용) 권한을 사용 하 여 Domain Users 그룹 추가</span><span class="sxs-lookup"><span data-stu-id="924f6-122">Add the Domain Users group with Read/Enroll (Allow) permissions</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

