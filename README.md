# universe.sql
Freecodecamp the Relational Data Base course -the first project in the course which is Celestials Bodies DATABASE

--
-- PostgreSQL database dump
--

-- Dumped from database version 12.9 (Ubuntu 12.9-2.pgdg20.04+1)
-- Dumped by pg_dump version 12.9 (Ubuntu 12.9-2.pgdg20.04+1)

SET statement_timeout = 0;
SET lock_timeout = 0;
SET idle_in_transaction_session_timeout = 0;
SET client_encoding = 'UTF8';
SET standard_conforming_strings = on;
SELECT pg_catalog.set_config('search_path', '', false);
SET check_function_bodies = false;
SET xmloption = content;
SET client_min_messages = warning;
SET row_security = off;

DROP DATABASE universe;
--
-- Name: universe; Type: DATABASE; Schema: -; Owner: freecodecamp
--

CREATE DATABASE universe WITH TEMPLATE = template0 ENCODING = 'UTF8' LC_COLLATE = 'C.UTF-8' LC_CTYPE = 'C.UTF-8';


ALTER DATABASE universe OWNER TO freecodecamp;

\connect universe

SET statement_timeout = 0;
SET lock_timeout = 0;
SET idle_in_transaction_session_timeout = 0;
SET client_encoding = 'UTF8';
SET standard_conforming_strings = on;
SELECT pg_catalog.set_config('search_path', '', false);
SET check_function_bodies = false;
SET xmloption = content;
SET client_min_messages = warning;
SET row_security = off;

SET default_tablespace = '';

SET default_table_access_method = heap;

--
-- Name: galaxy; Type: TABLE; Schema: public; Owner: freecodecamp
--

CREATE TABLE public.galaxy (
    galaxy_id integer NOT NULL,
    name character varying(30) NOT NULL,
    galaxy_history text NOT NULL,
    weight integer NOT NULL,
    most_popular integer NOT NULL
);


ALTER TABLE public.galaxy OWNER TO freecodecamp;

--
-- Name: galaxy_galaxy_id_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.galaxy_galaxy_id_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.galaxy_galaxy_id_seq OWNER TO freecodecamp;

--
-- Name: galaxy_galaxy_id_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.galaxy_galaxy_id_seq OWNED BY public.galaxy.galaxy_id;


--
-- Name: galaxy_most_popular_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.galaxy_most_popular_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.galaxy_most_popular_seq OWNER TO freecodecamp;

--
-- Name: galaxy_most_popular_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.galaxy_most_popular_seq OWNED BY public.galaxy.most_popular;


--
-- Name: galaxy_weight_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.galaxy_weight_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.galaxy_weight_seq OWNER TO freecodecamp;

--
-- Name: galaxy_weight_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.galaxy_weight_seq OWNED BY public.galaxy.weight;


--
-- Name: moon; Type: TABLE; Schema: public; Owner: freecodecamp
--

CREATE TABLE public.moon (
    moon_id integer NOT NULL,
    name character varying(30),
    moon_ray_in_km integer NOT NULL,
    planet_id integer NOT NULL,
    weight integer NOT NULL
);


ALTER TABLE public.moon OWNER TO freecodecamp;

--
-- Name: moon_moon_id_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.moon_moon_id_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.moon_moon_id_seq OWNER TO freecodecamp;

--
-- Name: moon_moon_id_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.moon_moon_id_seq OWNED BY public.moon.moon_id;


--
-- Name: moon_weight_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.moon_weight_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.moon_weight_seq OWNER TO freecodecamp;

--
-- Name: moon_weight_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.moon_weight_seq OWNED BY public.moon.weight;


--
-- Name: planet; Type: TABLE; Schema: public; Owner: freecodecamp
--

CREATE TABLE public.planet (
    planet_id integer NOT NULL,
    name character varying(30),
    planet_ray_in_km integer NOT NULL,
    star_id integer NOT NULL,
    weight integer NOT NULL
);


ALTER TABLE public.planet OWNER TO freecodecamp;

--
-- Name: planet_planet_id_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.planet_planet_id_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.planet_planet_id_seq OWNER TO freecodecamp;

--
-- Name: planet_planet_id_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.planet_planet_id_seq OWNED BY public.planet.planet_id;


--
-- Name: planet_weight_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.planet_weight_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.planet_weight_seq OWNER TO freecodecamp;

--
-- Name: planet_weight_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.planet_weight_seq OWNED BY public.planet.weight;


--
-- Name: star; Type: TABLE; Schema: public; Owner: freecodecamp
--

CREATE TABLE public.star (
    star_id integer NOT NULL,
    name character varying(30),
    star_dimensions_in_km numeric NOT NULL,
    galaxy_id integer,
    weight integer NOT NULL
);


ALTER TABLE public.star OWNER TO freecodecamp;

--
-- Name: star_star_id_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.star_star_id_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.star_star_id_seq OWNER TO freecodecamp;

--
-- Name: star_star_id_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.star_star_id_seq OWNED BY public.star.star_id;


--
-- Name: star_weight_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.star_weight_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.star_weight_seq OWNER TO freecodecamp;

--
-- Name: star_weight_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.star_weight_seq OWNED BY public.star.weight;


--
-- Name: statistics; Type: TABLE; Schema: public; Owner: freecodecamp
--

CREATE TABLE public.statistics (
    galaxy_id integer NOT NULL,
    star_available boolean NOT NULL,
    planet_available boolean NOT NULL,
    moon_available boolean NOT NULL,
    star_number integer,
    planet_number integer,
    moon_number integer,
    name character varying(30),
    statistics_id integer NOT NULL
);


ALTER TABLE public.statistics OWNER TO freecodecamp;

--
-- Name: statistics_statistics_id_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.statistics_statistics_id_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.statistics_statistics_id_seq OWNER TO freecodecamp;

--
-- Name: statistics_statistics_id_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.statistics_statistics_id_seq OWNED BY public.statistics.statistics_id;


--
-- Name: galaxy galaxy_id; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.galaxy ALTER COLUMN galaxy_id SET DEFAULT nextval('public.galaxy_galaxy_id_seq'::regclass);


--
-- Name: galaxy weight; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.galaxy ALTER COLUMN weight SET DEFAULT nextval('public.galaxy_weight_seq'::regclass);


--
-- Name: galaxy most_popular; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.galaxy ALTER COLUMN most_popular SET DEFAULT nextval('public.galaxy_most_popular_seq'::regclass);


--
-- Name: moon moon_id; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.moon ALTER COLUMN moon_id SET DEFAULT nextval('public.moon_moon_id_seq'::regclass);


--
-- Name: moon weight; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.moon ALTER COLUMN weight SET DEFAULT nextval('public.moon_weight_seq'::regclass);


--
-- Name: planet planet_id; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.planet ALTER COLUMN planet_id SET DEFAULT nextval('public.planet_planet_id_seq'::regclass);


--
-- Name: planet weight; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.planet ALTER COLUMN weight SET DEFAULT nextval('public.planet_weight_seq'::regclass);


--
-- Name: star star_id; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.star ALTER COLUMN star_id SET DEFAULT nextval('public.star_star_id_seq'::regclass);


--
-- Name: star weight; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.star ALTER COLUMN weight SET DEFAULT nextval('public.star_weight_seq'::regclass);


--
-- Name: statistics statistics_id; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.statistics ALTER COLUMN statistics_id SET DEFAULT nextval('public.statistics_statistics_id_seq'::regclass);


--
-- Data for Name: galaxy; Type: TABLE DATA; Schema: public; Owner: freecodecamp
--

INSERT INTO public.galaxy VALUES (7, 'voie lactée', 'it is the galaxy where the earth beyond to and it is the galaxy with most of informations its dimenssions is approxiamtely 180 IA', 1, 1);
INSERT INTO public.galaxy VALUES (8, 'DRACO', ' One of the nearest galaxy from "voie lactée" with a dimension of 120 IA', 2, 2);
INSERT INTO public.galaxy VALUES (9, 'galaxy naine de grand chien', 'the nearest galaxy from our galaxy no informations about its dimmenssions', 3, 3);
INSERT INTO public.galaxy VALUES (10, 'voie café', 'one of the most chill galaxy', 4, 4);
INSERT INTO public.galaxy VALUES (11, 'voie thé', 'one of the most boring galaxy', 5, 5);
INSERT INTO public.galaxy VALUES (12, 'voie nazale', 'all the galaxy hate this galaxy', 6, 6);


--
-- Data for Name: moon; Type: TABLE DATA; Schema: public; Owner: freecodecamp
--

INSERT INTO public.moon VALUES (62, 'moon 1', 1230, 5, 62);
INSERT INTO public.moon VALUES (63, 'moon 2', 12340, 6, 63);
INSERT INTO public.moon VALUES (64, 'moon 3', 12310, 7, 64);
INSERT INTO public.moon VALUES (65, 'moon 4', 12319, 8, 65);
INSERT INTO public.moon VALUES (66, 'moon 5', 1236, 9, 66);
INSERT INTO public.moon VALUES (67, 'moon 6', 1239, 10, 67);
INSERT INTO public.moon VALUES (68, 'moon 7', 1239, 11, 68);
INSERT INTO public.moon VALUES (69, 'moon 8', 1239, 12, 69);
INSERT INTO public.moon VALUES (70, 'moon 9', 1239, 11, 70);
INSERT INTO public.moon VALUES (71, 'moon 10', 12239, 12, 71);
INSERT INTO public.moon VALUES (72, 'moon 11', 1339, 5, 72);
INSERT INTO public.moon VALUES (73, 'moon 12', 1460, 6, 73);
INSERT INTO public.moon VALUES (74, 'moon 13', 1460, 7, 74);
INSERT INTO public.moon VALUES (75, 'moon 14', 1460, 13, 75);
INSERT INTO public.moon VALUES (76, 'moon 15', 1460, 14, 76);
INSERT INTO public.moon VALUES (77, 'moon 16', 1460, 15, 77);
INSERT INTO public.moon VALUES (78, 'moon 17', 1467, 16, 78);
INSERT INTO public.moon VALUES (80, 'moon 18', 1468, 9, 80);
INSERT INTO public.moon VALUES (81, 'moon 19', 1468, 13, 81);
INSERT INTO public.moon VALUES (82, 'moon 20', 1468, 16, 82);


--
-- Data for Name: planet; Type: TABLE DATA; Schema: public; Owner: freecodecamp
--

INSERT INTO public.planet VALUES (5, 'planet un', 18283, 1, 5);
INSERT INTO public.planet VALUES (6, 'planet deux', 37379, 1, 6);
INSERT INTO public.planet VALUES (7, 'planet troois', 73278, 2, 7);
INSERT INTO public.planet VALUES (8, 'planet four', 22333, 2, 8);
INSERT INTO public.planet VALUES (9, 'planet five', 727373, 3, 9);
INSERT INTO public.planet VALUES (10, 'planet six', 73829, 3, 10);
INSERT INTO public.planet VALUES (11, 'planet seven', 12333, 4, 11);
INSERT INTO public.planet VALUES (12, 'planet eight', 28383, 5, 12);
INSERT INTO public.planet VALUES (13, 'planet nine', 82828, 6, 13);
INSERT INTO public.planet VALUES (14, 'planet ten', 833990, 4, 14);
INSERT INTO public.planet VALUES (15, 'planet eleven', 83838, 6, 15);
INSERT INTO public.planet VALUES (16, 'planet twelve', 833990, 6, 16);


--
-- Data for Name: star; Type: TABLE DATA; Schema: public; Owner: freecodecamp
--

INSERT INTO public.star VALUES (1, 'dfbjj', 12889.34, 7, 1);
INSERT INTO public.star VALUES (2, 'star un', 18283.3, 8, 2);
INSERT INTO public.star VALUES (3, 'star deux', 37379.9, 9, 3);
INSERT INTO public.star VALUES (4, 'star troois', 73278.0, 10, 4);
INSERT INTO public.star VALUES (5, 'star four', 22333.2, 11, 5);
INSERT INTO public.star VALUES (6, 'star five', 727373, 12, 6);
INSERT INTO public.star VALUES (7, 'star six', 73829, 12, 7);


--
-- Data for Name: statistics; Type: TABLE DATA; Schema: public; Owner: freecodecamp
--

INSERT INTO public.statistics VALUES (7, true, true, true, 1, 2, 4, 'voie lactée', 2);
INSERT INTO public.statistics VALUES (10, true, true, true, 1, 1, 2, 'voie café', 3);
INSERT INTO public.statistics VALUES (8, true, true, true, 1, 2, 3, 'DRACO', 4);


--
-- Name: galaxy_galaxy_id_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.galaxy_galaxy_id_seq', 12, true);


--
-- Name: galaxy_most_popular_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.galaxy_most_popular_seq', 6, true);


--
-- Name: galaxy_weight_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.galaxy_weight_seq', 6, true);


--
-- Name: moon_moon_id_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.moon_moon_id_seq', 82, true);


--
-- Name: moon_weight_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.moon_weight_seq', 82, true);


--
-- Name: planet_planet_id_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.planet_planet_id_seq', 16, true);


--
-- Name: planet_weight_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.planet_weight_seq', 16, true);


--
-- Name: star_star_id_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.star_star_id_seq', 14, true);


--
-- Name: star_weight_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.star_weight_seq', 14, true);


--
-- Name: statistics_statistics_id_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.statistics_statistics_id_seq', 4, true);


--
-- Name: galaxy galaxy_pkey; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.galaxy
    ADD CONSTRAINT galaxy_pkey PRIMARY KEY (galaxy_id);


--
-- Name: galaxy galaxy_unique; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.galaxy
    ADD CONSTRAINT galaxy_unique UNIQUE (name);


--
-- Name: moon moon_pkey; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.moon
    ADD CONSTRAINT moon_pkey PRIMARY KEY (moon_id);


--
-- Name: moon moon_unique; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.moon
    ADD CONSTRAINT moon_unique UNIQUE (name);


--
-- Name: planet planet_pkey; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.planet
    ADD CONSTRAINT planet_pkey PRIMARY KEY (planet_id);


--
-- Name: planet planet_unique; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.planet
    ADD CONSTRAINT planet_unique UNIQUE (name);


--
-- Name: star star_pkey; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.star
    ADD CONSTRAINT star_pkey PRIMARY KEY (star_id);


--
-- Name: star star_unique; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.star
    ADD CONSTRAINT star_unique UNIQUE (name);


--
-- Name: statistics statistics_galaxy_name_key; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.statistics
    ADD CONSTRAINT statistics_galaxy_name_key UNIQUE (name);


--
-- Name: statistics statistics_pkey; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.statistics
    ADD CONSTRAINT statistics_pkey PRIMARY KEY (statistics_id);


--
-- Name: moon moon_planet_id_fkey; Type: FK CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.moon
    ADD CONSTRAINT moon_planet_id_fkey FOREIGN KEY (planet_id) REFERENCES public.planet(planet_id);


--
-- Name: planet planet_star_id_fkey; Type: FK CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.planet
    ADD CONSTRAINT planet_star_id_fkey FOREIGN KEY (star_id) REFERENCES public.star(star_id);


--
-- Name: star star_galaxy_id_fkey; Type: FK CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.star
    ADD CONSTRAINT star_galaxy_id_fkey FOREIGN KEY (galaxy_id) REFERENCES public.galaxy(galaxy_id);


--
-- Name: statistics statistics_galaxy_id_fkey; Type: FK CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.statistics
    ADD CONSTRAINT statistics_galaxy_id_fkey FOREIGN KEY (galaxy_id) REFERENCES public.galaxy(galaxy_id);


--
-- PostgreSQL database dump complete
--

