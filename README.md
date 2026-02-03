<?php

class Vehicule
    {
        protected string $marque;
        protected int $vitesse = 0;
        public static int $nbVehicule = 0;
        public function __construct(string $marque)
        {
            $this->marque = $marque;
            self::$nbVehicule += 1;
        }
        public function accelerer(int $vitesse) : void
        {
            $this->vitesse += $vitesse;
        }
        public function affiche() : void
        {
            echo "Marque de voiture : ".$this->marque.PHP_EOL;
        }
    };
    class Voiture extends Vehicule
    {
        private int $nbrePortes;
        public function __construct(string $marque, int $nbrePortes)
        {
            Vehicule::__construct($marque);
            $this->nbrePortes = $nbrePortes;
        }
        public function affiche() : void 
        {
            parent::affiche();
            echo "Nombre de portes : ".$this->nbrePortes.PHP_EOL;
        }
    };

    $v1 = new Vehicule("RANGE ROVER");
    $v2 = new Vehicule("FERRARI");
    $v1->affiche();
    $v2->affiche();
    echo Vehicule::$nbVehicule.PHP_EOL;
    interface monInterface {
        public function affiche (): void;
        public function carree (int $x): int;
    };

?>
