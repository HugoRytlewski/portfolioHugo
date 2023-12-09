
#Documentation des Fonctionnalités de Gestion des Factures

Ce document décrit les fonctionnalités implémentées pour la gestion des factures dans l'API du projet. Ces fonctionnalités permettent la création, la modification et la gestion des factures pour les congressistes.

##Création de Facture Automatisée

```php

if (isset($_POST['cr'])) {

    if (isset($_GET["id_congressiste"])){


    $congressiste=new Congressiste();

    $petitDej=$congressiste->aPrisPetitDejeuner($_GET["id_congressiste"]);

    if ($petitDej) {

        $PrixPetitDej=10;

    }else {

        $PrixPetitDej=0;

    }


    $activite=new Activite();

    $TotActiv=$activite->getTotalMontantActivites($_GET["create"]);


    $session=new Session();

    $TotSession=$session->getTotalMontantSessions($_GET["create"]);


    $congressiste=new Congressiste();

    $TotCong=$congressiste->getTotalMontantCongre($_GET["create"]);


    $participe=new Participe();

    $res=$participe->getIdActivitebyIDcongre($_GET["create"]);


    $Total=$TotActiv+$TotSession+$TotCong+$PrixPetitDej;

    $TotalFac=$TotActiv+$TotSession+$TotCong+$PrixPetitDej;


}


```

##Visualisation des Détails de la Facture

```php

if (isset($_GET["idd_congressiste"])){

    $facture=new facturation();

    $UneFactureId=$facture->GetOneFacture($_GET["id"]);


    $valeur_bool=$UneFactureId->StatutPaiement;


    $activite=new Activite();

    $TotActiv=$activite->getTotalMontantActivites($_GET["idd_congressiste"]);


    $session=new Session();

    $TotSession=$session->getTotalMontantSessions($_GET["idd_congressiste"]);


    $congressiste=new Congressiste();

    $TotCong=$congressiste->getTotalMontantCongre($_GET["idd_congressiste"]);


    $congressiste=new Congressiste();

    $petitDej=$congressiste->aPrisPetitDejeuner($_GET["idd_congressiste"]);

    if ($petitDej) {

        $PrixPetitDej=10;

    }else {

        $PrixPetitDej=0;

    }

    $participe=new Participe();

    $res=$participe->getIdActivitebyIDcongre($_GET["idd_congressiste"]);


    $TotalModif=$TotActiv+$TotSession+$TotCong  +$PrixPetitDej;


    $DetailFacture=$facture->GetAllDetailFacture($_GET["id"]);

}

```

##Creation pdf de la Facture

```php

if (isset($_GET['pdf'])){

    $pdf=new FPDF();

    $pdf->AddPage();

    $euro=iconv('utf-8','cp1252','€');



    $pdf->SetFont('Arial','B',18);

    $pdf->Cell(0,10,'Details de la facture',0,1,'C');

    $pdf->Ln(10);


    $pdf->SetFont('Arial','',12);


    $pdf->Cell(0,10,'Nom: '.$DetailFacture['congres'][0]->Nom,0,1);

    $pdf->Cell(0,10,'Prenom: '.$DetailFacture['congres'][0]->Prenom,0,1);



    $pdf->Cell(0,10,'Hotel: '.$DetailFacture['congres'][0]->NomHotel,0,1);


    if ($DetailFacture['congres'][0]->Dejeuner==1) {

        $pdf->Cell(0,10,'Option : Dejeuner inclus + 10'.$euro,0,1);

    }


    $pdf->Cell(0,10,'Date: '.$DetailFacture['congres'][0]->Date,0,1);


    $pdf->SetFont('Arial','B',14);

    $pdf->Cell(0,10,'Activites:',0,1);

    $pdf->SetFont('Arial','',12);


    foreach ($DetailFacture['activites'] as$uneActivite) {

        $pdf->Cell(0,10,$uneActivite['NomActivite'].' - Montant: '.$uneActivite['MontantActivite'].$euro,0,1);

    }


    $pdf->SetFont('Arial','B',14);

    $pdf->Cell(0,10,'Sessions:',0,1);

    $pdf->SetFont('Arial','',12);



    foreach ($DetailFacture['sessions'] as$uneSession) {

        $pdf->Cell(0,10,$uneSession['NomSession'].' - Montant: '.$uneSession['MontantSession'].$euro,0,1);

    }


    if ($DetailFacture['congres'][0]->Dejeuner==1) {

        $pdf->Cell(0,10,'Detail Prix:  Activites :'.$TotActiv.$euro.' + Sessions : '.$TotSession.$euro.' + Hotel: '.$TotCong.$euro.' + Petit dejeuner : 10'.$euro,0,1);


    }else{

    $pdf->Cell(0,10,'Detail Prix:  Activites :'.$TotActiv.$euro.' + Sessions : '.$TotSession.$euro.' + Hotel: '.$TotCong.$euro,0,1);

}

    $pdf->SetFont('Arial','B',16);

    $pdf->Cell(0,10,'Total Prix: '.$TotalModif.$euro,0,1);


    $pdf->Output("C:\\wamp64\\www\\ap\\facture\\".$DetailFacture['congres'][0]->Nom."detail_facture.pdf",'F');





}

```

##Auteur

Ce projet a été réalisé par [Hugo Rytlewski](https://www.linkedin.com/in/hugo-rytlewski-b06841281/).
